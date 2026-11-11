# Sitemap & Information Architecture: kutzen.org

## 1. Overview & Information Architecture

This document defines the complete page hierarchy, navigation structure, URL routing, and asset mapping for **kutzen.org**.

The site's architecture serves two distinct modes defined in `VISION.md`:
1. **The Polished Portfolio**: Direct, friction-free paths to professional credentials, scientific research, open-source software, and contact channels for collaborators, employers, and colleagues.
2. **The Poetry Notebook**: Thoughtful, reflective spaces for essays (*Reading Frames*), poetry, self-hosted systems experiments, and personal curiosity.

---

## 2. Global Navigation System

### 2.1 Primary Top Navigation Bar (`navbar`)
Configured in `_quarto.yml`, the top navigation bar is persistent across all pages, provides built-in search, and links to the primary content sections:

| Label | Source File | Public Route | Description / Purpose |
| :--- | :--- | :--- | :--- |
| **Dalton Kutzen** | `index.qmd` | `/` | Brand title link returning to the homepage |
| **Home** | `index.qmd` | `/` (`/index.html`) | Personal introduction & research overview |
| **About** | `about.qmd` | `/about.html` | Narrative background, skills matrix & current directions |
| **Projects** | `projects/index.qmd` | `/projects/` | Computational biology tools, workflows & systems |
| **Blog** | `blog/index.qmd` | `/blog/` | *Reading Frames* technical essays & learning notes |
| **CV** | `cv.qmd` | `/cv.html` | Portal for one-page Résumé and full Academic CV |
| **Contact** | `contact.qmd` | `/contact.html` | Direct communication channels & collaboration guidelines |
| **Search** | *(Built-in)* | Modal / Overlay | Client-side full-text search index (`search.json`) |
| **GitHub** *(Tool)* | External | `https://github.com/DKutzen22/kutzen.org` | Direct link to the site's open-source source repository |

### 2.2 Global Page Footer (`page-footer`)
The footer provides secondary discovery, academic citations, formal compliance, and syndication:

- **Left (Attribution & Colophon)**:
  - `© 2026 Dalton Kutzen · Made with Quarto`
- **Center (Social & Academic Identity Icons)**:
  - Accessibility Commitment: `/accessibility.html` (`fa universal-access`)
  - LinkedIn: `https://linkedin.com/in/daltonkutzen` (`fa brands linkedin`)
  - GitHub: `https://github.com/dkutzen22` (`fa brands github`)
  - ORCID: `https://orcid.org/0009-0009-2643-8127` (`ai orcid`)
  - Google Scholar: `https://scholar.google.com/citations?user=CIkLbu4AAAAJ` (`ai google-scholar`)
- **Right (Legal, Meta & Syndication)**:
  - Accessibility Statement: `/accessibility.html`
  - Contact Form / Guidelines: `/contact.html`
  - Creative Commons License: `/license.html`
  - RSS / Atom Feed: `/blog.xml` (or `/blog/index.xml`)

---

## 3. Complete Page Routing & Directory Structure

```
kutzen.org/
│
├── / (index.html)                          # Home: Personal introduction & quick links
├── /about.html                             # About: Detailed background, research & homelab
│
├── /projects/                              # Projects directory
│   ├── index.html                          # Featured workflows, tools & repositories
│   └── papertrail/                         # Project: Résumé-as-code template
│       └── index.html                      # Deep-dive article & documentation
│
├── /blog/                                  # "Reading Frames" blog listing
│   ├── index.html                          # Chronological post index & category listing
│   ├── index.xml / blog.xml                # RSS/Atom web syndication feed
│   └── 2026-10_why_homelab/                # Article: Homelab & self-hosted infrastructure
│       └── index.html                      # Article content
│
├── /cv.html                                # Résumé and Curriculum Vitae download portal
├── /contact.html                           # Contact methods, issues & feedback
├── /poem.html                              # Creative writing / poetry display ("What Remains")
│
├── /accessibility.html                     # Accessibility commitment, standards & reporting
├── /license.html                           # Creative Commons Attribution-ShareAlike 4.0
└── /404.html                               # Not Found error page with navigation recovery
```

---

## 4. Detailed Page Specifications

### 4.1 Homepage
- **Source**: `index.qmd`
- **Route**: `/` (`/index.html`)
- **Layout Template**: Quarto `jolla` template
- **Primary Elements**:
  - Centered circular portrait: `assets/images/headshot_1.jpg`
  - Bio introducing molecular biology studies at BYU, phage genomics, scientific software, and self-hosted systems
  - Quick action links: LinkedIn, GitHub, Email (`dalton@kutzen.org`)
- **Role**: Warm, low-cognitive-load front door that sets expectations and points visitors deeper.

### 4.2 About Page
- **Source**: `about.qmd`
- **Route**: `/about.html`
- **Layout**: Custom full-width container (`max-width: 1080px`) with scoped responsive CSS grid
- **Key Sections**:
  1. *Hero*: "Hi, I’m Dalton." with subtitle "Molecular biology, computational tools, and an assortment of side projects."
  2. *Connecting biology and computation*: Philosophy on bacteriophage genomics and reproducible computational research.
  3. *What I’m building*: Featured cards for Phantom (Snakemake workflow), genome visualization tools (R/Python), and homelab systems.
  4. *Skills & tools*: 4-quadrant responsive card grid (Bioinformatics/Genomics, Programming/Data Analysis, Research Software/Reproducibility, Systems/Infrastructure).
  5. *What I’m learning next*: Mathematical foundations (statistics, linear algebra, ML), package development, and GitOps/Kubernetes.
  6. *Beyond the technical side*: Personal interests—poetry, music, anime, games, and hardware repurposing.

### 4.3 Projects Index & Deep Dives
- **Source**: `projects/index.qmd`
- **Route**: `/projects/` (`/projects/index.html`)
- **Role**: Central gallery for computational biology software, bioinformatics pipelines, and open-source infrastructure.
- **Projects**:
  - **Papertrail** (`projects/papertrail/index.qmd`): Reproducible résumé-as-code template turning structured YAML into polished PDFs with Quarto and Typst.
  - *Future Additions*: Phantom (Snakemake phage workflow), anchor-op (Perturb-seq benchmark), phage visualization tools, and homelab infrastructure.

### 4.4 Blog: *Reading Frames*
- **Source Directory**: `blog/`
- **Main Index**: `blog/index.qmd` (`/blog/`)
- **Metadata**: `blog/_metadata.yml` (configuring comments, social share, canonical links)
- **Syndication**: `blog.xml` / `blog/index.xml` (RSS feed)
- **Current Articles**:
  - **Why do I have a Homelab?** (`blog/2026-10_why_homelab/index.qmd`):
    - *Categories*: `homelab`, `infrastructure-as-code`
    - *Topic*: Personal motivations, hardware experimentation, and systems learning.

### 4.5 Résumé & Academic CV
- **Source**: `cv.qmd`
- **Route**: `/cv.html`
- **Role**: Gateway to formal career and academic credentials.
- **Downloads Available**:
  - **One-page Résumé (PDF)**: `/assets/docs/Dalton_Kutzen-Resume.pdf` (tailored for industry / software / engineering roles)
  - **Curriculum Vitae (PDF)**: `/assets/docs/Dalton_Kutzen-CV.pdf` (comprehensive record of academic background, research, publications, and service)

### 4.6 Contact & Collaboration
- **Source**: `contact.qmd`
- **Route**: `/contact.html`
- **Layout Template**: Quarto `jolla` template
- **Channels**:
  - Email: `dalton@kutzen.org` (primary channel for research and collaboration)
  - GitHub: `https://github.com/dkutzen22` (issue tracking for bugs and software questions)
  - Website Issues: Direct link to repository issue tracker for reporting broken links or accessibility barriers

### 4.7 Poetry & Creative Writing
- **Source**: `poem.qmd`
- **Route**: `/poem.html`
- **Design Archetype**: Literary notebook presentation using `.poem` class and serif typography (Georgia / Times New Roman)
- **Current Content**: *"What Remains"* (stanzas exploring transience and memory)
- **Role**: Concrete fulfillment of the "half poetry notebook" identity without diluting scientific rigor.

### 4.8 Compliance & Utility Pages
- **Accessibility** (`accessibility.qmd` -> `/accessibility.html`):
  - Outlines accessibility principles (contrast, keyboard navigation, alternative text).
  - Acknowledges ongoing evolution and provides a direct issue-submission route.
- **License** (`license.qmd` -> `/license.html`):
  - Formal Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) release for blog content.
- **404 Not Found** (`404.qmd` -> `/404.html`):
  - Clean error recovery screen providing immediate links back to homepage and search.

---

## 5. Static Assets & Media Mapping

| Path | Purpose / Description |
| :--- | :--- |
| `assets/docs/Dalton_Kutzen-Resume.pdf` | Industry/professional one-page résumé download |
| `assets/docs/Dalton_Kutzen-CV.pdf` | Comprehensive academic curriculum vitae download |
| `assets/images/headshot_1.jpg` | Primary round headshot for landing page (`index.qmd`) |
| `assets/images/headshot_2.jpg` | Secondary alternate portrait |
| `assets/images/logo.svg` | Site brandmark / logo vector |
| `assets/styles.css` | Global styling overrides (poetry, footer icons, focus rings) |
| `assets/custom.scss` | SCSS rules for dark mode code syntax highlighting |
| `assets/listing-default.css` | Custom styling for Quarto card listings and title headers |
| `brand/_brand.yml` | Central brand token definitions (colors, fonts, sizes) |

---

## 6. External Links & Academic Graph

The site connects Dalton Kutzen to established academic, professional, and code ecosystems:

| Platform | Target URL | Context / Role |
| :--- | :--- | :--- |
| **GitHub Profile** | `https://github.com/dkutzen22` | Code author, open source projects |
| **Site Repository** | `https://github.com/DKutzen22/kutzen.org` | Source code for this Quarto website |
| **LinkedIn** | `https://www.linkedin.com/in/daltonkutzen/` | Professional networking |
| **ORCID** | `https://orcid.org/0009-0009-2643-8127` | Persistent researcher identifier |
| **Google Scholar** | `https://scholar.google.com/citations?user=CIkLbu4AAAAJ` | Citation indexing & scholarly publications |
| **Email** | `mailto:dalton@kutzen.org` | Direct contact address |

---

## 7. Content Governance & Expansion Rules

Per `AGENTS.md` and `VISION.md`, future updates to the sitemap must adhere to these policies:

1. **Top-Level Navigation Invariance**:
   - Do not alter top-level navbar routes (`Home`, `About`, `Projects`, `Blog`, `CV`, `Contact`) without explicit approval.
2. **Slug Consistency**:
   - Use lowercase, kebab-case directory slugs for new projects (`projects/<project-name>/index.qmd`) and date-prefixed slugs for blog posts (`blog/YYYY-MM_<slug>/index.qmd`).
3. **Preserve Creative Work**:
   - Keep creative writing and poetry accessible; never demote or hide creative sections solely to enforce conventional corporate norms.
4. **Link Integrity**:
   - When renaming or retiring any public page path, create proper redirects or verify all internal links in `_quarto.yml`, markdown content, and templates.
