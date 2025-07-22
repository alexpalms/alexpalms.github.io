---
# Leave the homepage title empty to use the site title
title: "Alessandro Palmas"
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ""
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/PALMAS_Resume_2025.pdf
    design:
      css_class: dark
      background:
        color: black
        image:
          # Add your image background to `assets/media/`.
          filename: montreal.jpg
          filters:
            brightness: 0.25
          size: cover
          position: center
          parallax: false
  #- block: markdown
  #  content:
  #    title: '📚 My Research'
  #    subtitle: ''
  #    text: |-
  #      Use this area to speak to your mission. I'm a research scientist in the Moonshot team at DeepMind. I blog about machine learning, deep learning, and moonshots.
  #
  #      I apply a range of qualitative and quantitative methods to comprehensively investigate the role of science and technology in the economy.
  #
  #      Please reach out to collaborate 😃
  #  design:
  #    columns: '1'
  - block: collection
    content:
      title: Open Source Projects
      text: Building is the fastest way to learn.
      count: 3
      filters:
        folders:
          - projects
        featured_only: false
    design:
      view: article-grid
      fill_image: false
      columns: 3
  - block: home-experience
    content:
      username: admin
    design:
      # Hugo date format
      date_format: 'January 2006'
      # Education or Experience section first?
      is_education_first: false
  - block: collection
    content:
      title: Papers
      text: ""
      filters:
        folders:
          - papers
        exclude_featured: false
    design:
      view: citation
---
