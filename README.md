# kutzen.org

The personal website, scientific portfolio, and creative notebook of **Dalton Kutzen** — molecular biology student and bioinformatics researcher at Brigham Young University.

Live site: [**kutzen.org**](https://www.kutzen.org) · Repository: [**DKutzen22/kutzen.org**](https://github.com/DKutzen22/kutzen.org)

---

## Overview & Vision

As articulated in [`VISION.md`](VISION.md), this website is built around a distinct central idea:

> **"Half polished portfolio and half notebook, with room for the research and projects I love."**

Rather than functioning as a sterile corporate portfolio or an extended résumé, `kutzen.org` brings together:
- **Scientific research & computational workflows**: Bacteriophage genomics, single-cell Perturb-seq modeling, and reproducible pipeline design.
- **Open-source software**: Tools and frameworks that turn ideas into reproducible software (such as [Papertrail](https://github.com/dkutzen22/papertrail)).
- **Systems & infrastructure**: Hands-on write-ups detailing self-hosted Linux servers, Proxmox virtualization, containerization, and networking.
- **Essays & reflections (*Reading Frames*)**: Technical articles and long-form writing on living systems and computation.
- **Creative writing & poetry**: Dedicated spaces for creative reflection, formatted with classical serif typography.
- **Credentials & contact**: Direct access to downloadable résumé and academic CV PDFs, plus direct communication channels.

---

## Technology Stack

The site is built with **[Quarto](https://quarto.org/)** and rendered into a static site hosted with clean semantic HTML, CSS, and modern web standards.

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Site Engine** | [Quarto](https://quarto.org/) (v1.6+) | Markdown-based scientific publishing system |
| **Brand System** | [`brand/_brand.yml`](brand/_brand.yml) | Central design tokens, color palette, and font definitions |
| **Typography** | Google Fonts | **Raleway** (headings), **Nunito** (body), **IBM Plex Mono** (code) |
| **Styling & Themes** | Bootstrap 5 + SCSS | Dual themes: `flatly` (light) & `darkly` + `assets/custom.scss` (dark) |
| **Syntax Highlighting** | Custom "Quiet Dark" SCSS | Soft, low-fatigue syntax token styling optimized for `#1b1b1b` code blocks |
| **Accessibility** | Axe Core (`axe: true`) | Automated WCAG accessibility evaluation during builds |
| **Syndication** | RSS / Atom (`blog.xml`) | Automatic web feeds for blog publications |

### Installed Quarto Extensions

The repository integrates several specialized extensions under `_extensions/`:
- **[`quarto-ext/fontawesome`](https://github.com/quarto-ext/fontawesome)** & **[`schochastics/academicons`](https://github.com/schochastics/academicons)**: Web and academic iconography (ORCID, Google Scholar, GitHub, LinkedIn).
- **[`jmbuhr/molstar`](https://github.com/jmbuhr/quarto-molstar)**: Embedded interactive 3D biomolecular structure viewer (Mol*).
- **[`coatless-quarto/pyodide`](https://github.com/coatless-quarto/pyodide)**: In-browser client-side Python code execution.
- **[`ryjohnson09/git-sandbox`](https://github.com/ryjohnson09/git-sandbox)**: Interactive Git environment demonstrations.
- **[`EmilHvitfeldt/diagrams`](https://github.com/EmilHvitfeldt/quarto-diagrams)** & **[`timeline`](https://github.com/EmilHvitfeldt/quarto-timeline)**: Workflow and pipeline visualizations.

---

## Repository Structure

```text
kutzen.org/
├── _quarto.yml             # Global Quarto website configuration
├── index.qmd               # Landing page (Jolla introduction)
├── about.qmd               # Narrative background, skills matrix & philosophy
│
├── projects/               # Projects gallery & deep dives
│   ├── index.qmd           # Gallery grid listing
│   └── papertrail/         # Featured project: Résumé-as-code template
│       ├── index.qmd       # Project deep-dive article
│       └── featured.svg    # Vector preview graphic
│
├── blog/                   # "Reading Frames" publication
│   ├── index.qmd           # Chronological article listing & RSS feed
│   ├── _metadata.yml       # Blog-wide metadata (comments, share, canonical)
│   └── 2026-10_why_homelab/# Featured essay: "Why do I have a Homelab?"
│       ├── index.qmd       # Essay content
│       └── featured.jpg    # Article photography (Taylor Vick / Unsplash)
│
├── cv.qmd                  # Curriculum Vitae and Résumé download portal
├── contact.qmd             # Direct contact channels & collaboration context
├── poem.qmd                # Creative writing notebook (serif poetry display)
│
├── accessibility.qmd       # Accessibility commitment & feedback reporting
├── license.qmd             # Content licensing details (CC BY-SA 4.0)
├── 404.qmd                 # Custom error page
│
├── brand/
│   └── _brand.yml          # Design system tokens (colors, fonts, semantics)
├── assets/
│   ├── custom.scss         # Quiet dark syntax palette for code blocks
│   ├── styles.css          # Global styles (poetry, buttons, footer icons)
│   ├── listing-default.css # Styling for listing cards and title blocks
│   ├── docs/               # PDF documents (Dalton_Kutzen-Resume.pdf, CV.pdf)
│   └── images/             # Portraits (headshot_1.jpg, headshot_2.jpg, logo.svg)
│
├── VISION.md               # Guiding vision, priorities, and non-goals
├── DESIGN.md               # Complete design system and styling reference
├── CONTENT.md              # Voice, factual integrity, and editorial guidelines
├── ARCHITECTURE.md         # Full sitemap, routing tables, and asset inventory
└── AGENTS.md               # Working standards and boundaries for AI agents
```

---

## Local Development & Build

### Prerequisites
1. **[Quarto CLI](https://quarto.org/docs/get-started/)** (version 1.6 or higher).
2. **Git** for version control.

### Running the Development Server
Preview the site locally with live reloading:

```bash
quarto preview
```

By default, the preview server binds to `http://127.0.0.1:4200` as configured in `_quarto.yml`. Any changes to `.qmd`, `.yml`, `.scss`, or `.css` files automatically recompile and update in your browser.

### Building the Static Site
Render the full site to the `_site/` directory:

```bash
quarto render
```

To render an individual page during development:

```bash
quarto render about.qmd
quarto render projects/papertrail/index.qmd
quarto render blog/2026-10_why_homelab/index.qmd
```

---

## Documentation Ecosystem

The repository maintains five foundational governance documents:

1. [**`VISION.md`**](VISION.md): Defines the core purpose, audience, guiding principles, and non-goals of the website.
2. [**`DESIGN.md`**](DESIGN.md): Details the design system, color tokens, typography hierarchy, dual light/dark themes, and component styling.
3. [**`CONTENT.md`**](CONTENT.md): Outlines the personal voice, editorial standards, factual integrity rules, and tone across different content registers.
4. [**`ARCHITECTURE.md`**](ARCHITECTURE.md): Authoritative reference for the site map, URL paths, content directories, and asset locations.
5. [**`AGENTS.md`**](AGENTS.md): Prescribes behavioral boundaries, safety rules, and validation protocols for automated coding assistants.

---

## Licensing

- **Writing & Articles**: The essays and blog posts in [`blog/`](blog/) are released under a [Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)](http://creativecommons.org/licenses/by-sa/4.0/) (see [`license.qmd`](license.qmd)).
