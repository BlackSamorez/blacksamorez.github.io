---
# Leave the homepage title empty to use the site title
title: ''
date: 2022-10-24
type: landing

sections:
  - block: about.biography
    id: about
    content:
      title: Biography
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin

  - block: experience
    content:
      title: Experience
      # Date format for experience
      #   Refer to https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Experiences.
      #   Add/remove as many `experience` items below as you like.
      #   Required fields are `title`, `company`, and `date_start`.
      #   Leave `date_end` empty if it's your current employer.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - title: Senior ML Engineer (NLP)
          company: Wildberries
          company_url: https://wildberries.ru/
          company_logo: wildberries
          location: Remote
          date_start: '2024-04-16'
          date_end: ''
          description: |2-
            * Overseeing the LLM deployment
        - title: ML Research Scientist
          company: Yandex Research
          company_url: https://research.yandex.com/
          company_logo: yandex
          location: Moscow, Russia
          date_start: '2023-11-14'
          date_end: '2024-02-15'
          description: |2-
            * Wrote a first-author [paper on _LLM Compression_](https://arxiv.org/abs/2401.06118)
            * Achieved _state-of-the-art_ results on _LLM_ compression, reducing model size by _87%_ with acceptable loss in performance
            * Wrote efficient inference kernels using _Triton_ and _C++_, speeding up _LLM_ inference by up to _320%_
            * Integrated the framework into the _transformers_ library, enabling low RAM dispatch and reducing instance RAM requirements by _70%_
        - title: Research Intern
          company: KAUST, Optimization and Machine Learning Lab
          company_url: ''
          company_logo: kaust
          location: Saudi Arabia
          date_start: '2023-07-10'
          date_end: '2023-09-30'
          description: |2-
            * Conducted research under the supervision of _Prof. Peter Richtárik_.
            * Authored a first-author [paper on _Correlated Quantization_](https://arxiv.org/abs/2401.05518)
        - title: Infrastructure Developer
          company: Eqvilent (HFT Fund)
          company_url: ''
          location: Remote
          date_start: '2022-07-01'
          date_end: '2023-03-01'
        - title: ML Engineer Intern (NLP)
          company: Yandex
          company_url: ''
          company_logo: yandex
          location: Moscow, Russia
          date_start: '2022-03-08'
          date_end: '2022-07-05'
          description: |2-
            * Enabled abstract _tabular data_ insertion for efficient _map-reduce_ _LLM_ inference, speeding up the tabular data processing by 120%
            * Increased test coverage of the _map-reduce_ inference interface from _0 to 85%_ through rigorous unit testing
        - title: Researcher
          company: Terra Quantum AG
          company_url: https://terraquantum.swiss/
          company_logo: tq-black
          location: Moscow, Russia
          date_start: '2020-07-01'
          date_end: '2022-07-31'
          description: |2-
            * Researched _quantum algorithms_ for business applications.
            * Developed an NMR spectra analysis toll, allowing for its use for for quantum computations.
            * Optimized _LLM_ deployment for chat assistant applications, reducing latency by 40%.
    design:
      columns: '1'
  - block: accomplishments
    content:
      # Note: `&shy;` is used to add a 'soft' hyphen in a long heading.
      title: 'Accomplish&shy;ments'
      subtitle:
      # Date format: https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `item` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - date_end: ''
          date_start: '2019-07-16'
          description: Gold Medal
          icon: ipho
          organization: Israel
          title: International Physics Olympiad
    design:
      columns: '2'
  - block: collection
    id: posts
    content:
      title: Recent Posts
      subtitle: ''
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        folders:
          - post
        author: ""
        category: ""
        tag: ""
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: compact
      columns: '2'
  - block: portfolio
    id: projects
    content:
      title: Projects
      filters:
        folders:
          - project
      # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
      default_button_index: 0
      # Filter toolbar (optional).
      # Add or remove as many filters (`filter_button` instances) as you like.
      # To show all items, set `tag` to "*".
      # To filter by a specific tag, set `tag` to an existing tag name.
      # To remove the toolbar, delete the entire `filter_button` block.
      buttons:
        - name: All
          tag: '*'
        - name: Deep Learning
          tag: Deep Learning
        - name: Other
          tag: Demo
    design:
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '1'
      view: showcase
      # For Showcase view, flip alternate rows?
      flip_alt_rows: false
---
