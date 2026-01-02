---
title: "🐋 ContaineRL - Containerize your RL Environments and Agents"
summary: How I built ContaineRL, a lightweight toolkit to package RL environments and agents as reproducible, containerized services, exposing them via gRPC with a clean Python API and CLI. It enables modular, language-agnostic RL pipelines, supports scalable deployment, and enforces strong engineering practices (type checking, testing, CI) without sacrificing developer ergonomics.
date: 2025-11-01
math: true
authors:
  - admin
tags:
  - Deep Reinforcement Learning
  - Containers
  - Docker
  - gRPC
image:
  caption: ''
draft: false

url_code: "https://github.com/alexpalms/containerl"
url_pdf:
url_video: ''

---

<div style="display: flex; justify-content: center; gap: 20px; margin-bottom: 0px; margin-top: 0px;">
  <a href="https://github.com/alexpalms/containerl" target="_blank">
    <img style="margin-top:0px; margin-bottom:10px;" src="https://img.shields.io/badge/code-github-blue?logo=github&labelColor=grey" alt="Code" />
  </a>
</div>

**TL;DR**: *How I built ContaineRL, a lightweight toolkit to **package RL environments and agents as reproducible, containerized services**, exposing them via **gRPC with a clean Python API and CLI**. It enables modular, language-agnostic RL pipelines, supports scalable deployment, and enforces strong engineering practices (type checking, testing, CI) without sacrificing developer ergonomics*

### Introduction

Modern reinforcement learning workflows increasingly span multiple systems: simulators, training pipelines, evaluation services, and deployment infrastructure. In practice, RL environments and agents are often tightly coupled to a single codebase, Python runtime, or execution context, making them difficult to reuse, scale, or integrate into production systems.

**ContaineRL** was designed to address this gap.

The goal of the project is simple but ambitious: **treat RL environments and agents as first-class, containerized services, with**:

- clean, strongly-typed interfaces
- reproducible execution
- minimal assumptions about the training stack
- easy local and CI-driven workflows

Instead of embedding environments and agents directly into training loops, ContaineRL allows them to be **exposed over gRPC**, packaged in Docker images, and orchestrated like any other microservice.

This approach enables:
- decoupled training and simulation
- scalable experimentation
- cross-language interoperability
- production-grade deployment patterns for RL systems

###  How ContaineRL Improves Quality-Of-Life

Most RL tooling assumes a monolithic setup:
- the environment lives in the same process as the agent
- the simulator shares memory with the learner
- scaling requires bespoke infrastructure glue

This breaks down quickly when:
- environments are heavy or simulator-bound
- agents must run remotely (or on different hardware)
- multiple learners need to interact with the same environment
- CI, reproducibility, or security boundaries matter

ContaineRL reframes the problem: **An environment or an agent is just a service with a well-defined contract.**

By containerizing these components:
- environments become reproducible artifacts
- agents can be swapped, scaled, or versioned independently
- training systems can remain lightweight and flexible

This design is particularly useful in:
- distributed RL
- simulation-heavy domains
- benchmarking and evaluation pipelines
- research-to-production transitions

### Architecture Overview

At its core, ContaineRL provides **two symmetric abstractions**:
- **Containerized Environments**
- **Containerized Agents**

Both are exposed via **gRPC**, with serialization handled through **msgpack-compatible types**, and both are managed through the same lifecycle primitives.

The system is composed of three main layers:

- **Python API** - minimal abstractions to wrap environments and agents
- **Transport Layer** - gRPC interfaces for interaction
- **CLI Tooling** - build, run, test, and manage containers



### Exposing an Environment as a Service

Any Gymnasium-compatible environment can be wrapped and exposed with minimal boilerplate.

```python
import gymnasium as gym
from containerl import create_environment_server

class Environment(gym.Env):
    def __init__(self, render_mode: str, env_name: str):
        self._env = gym.make(env_name, render_mode=render_mode)
        self.observation_space = gym.spaces.Dict({
            "observation": self._env.observation_space
        })
        self.action_space = self._env.action_space

    def reset(self, *, seed=None, options=None):
        obs, info = self._env.reset(seed=seed, options=options)
        return {"observation": obs}, info

    def step(self, action):
        obs, reward, terminated, truncated, info = self._env.step(action)
        return {"observation": obs}, float(reward), terminated, truncated, info

if __name__ == "__main__":
    create_environment_server(Environment)
```

Once containerized, this environment:
- listens on a fixed gRPC port
- accepts initialization arguments remotely
- can be run locally, in CI, or on a cluster

The environment process is **fully isolated**, making execution deterministic and reproducible.

### Exposing an Agent as a Service

Agents follow the same philosophy. Any policy or controller implementing the `CRLAgent` interface can be served as a container.

```python
import numpy as np
from gymnasium import spaces
from containerl import CRLAgent, create_agent_server

class Agent(CRLAgent):
    def __init__(self, target: float, gain: float):
        self.target = target
        self.gain = gain
        self.observation_space = spaces.Dict({
            "state": spaces.Box(0, 100, shape=(1,))
        })
        self.action_space = spaces.Box(0, 10, shape=(1,), dtype=np.float32)

    def get_action(self, observation):
        return np.clip(
            self.gain * (self.target - observation["state"]),
            0, 10
        )

if __name__ == "__main__":
    create_agent_server(Agent)
```

This makes it possible to:
- deploy agents independently of training code
- run agents on specialized hardware
- test policies via standardized client interfaces

### CLI-Driven Workflow

ContaineRL includes a CLI (`containerl-cli`) to manage the full lifecycle of containerized components.

Build an image:
```bash
uv run containerl-cli build ./examples/gymnasium/environments/atari/ \
  -n my-image -t v1
```

Run one or more containers:
```bash
uv run containerl-cli run my-image:v1 --count 3
```

Test connectivity and correctness:
```bash
uv run containerl-cli build-run-test ./examples/gymnasium/environments/atari/
```

This enables:
- fast local iteration
- reproducible CI checks
- automated validation of containers before deployment

### Key Takeaways

- **ContaineRL decouples RL components cleanly**, enabling modular and scalable systems.
- **Containerized environments and agents** become reusable, versioned artifacts.
- **gRPC-based interfaces** allow language-agnostic integration.
- **Strong engineering discipline** ensures reliability without hurting developer velocity.

This project reflects my broader approach to RL systems: **treat learning components as deployable, testable infrastructure**, not just Python objects inside a training loop.

### References

- 👨🏽‍💻 GitHub Code: https://github.com/alexpalms/containerl
- 📦 PyPI Package: https://pypi.org/project/containerl/
