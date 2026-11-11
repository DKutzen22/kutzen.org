# Agent Instructions for kutzen.org

## Project Identity

kutzen.org is Dalton Kutzen's personal and academic website.

It communicates what a résumé and LinkedIn profile cannot:
the depth behind my projects, the research I care about,
my writing, and what I am passionate about.

The central idea is:

> Half polished portfolio and half poetry notebook, with room
> for the research and projects I love.

The site serves future employers and coworkers, as well as
anyone curious about me.

Introduce me clearly, then offer paths into deeper material.
Do not make the entire site feel like a job application.

## Read Before Working

Read the root-level documents relevant to the task:

- `VISION.md`: purpose, audience, priorities, and non-goals.
- `DESIGN.md`: visual direction, themes, typography, and layouts.
- `CONTENT.md`: voice, factual integrity, and editorial boundaries.
- `ARCHITECTURE.md`: implementation structure and sitemap.
- `README.md`: setup, development, and deployment instructions.

Check for more specific `AGENTS.md` instructions in the
directories you modify.

Do not assume these documents all exist. Report a missing
document only when it materially affects the task.

### Resolving Conflicts

Explicit instructions for the current task take precedence
over general project guidance.

Otherwise:
- Use `VISION.md` to understand intent.
- Use `DESIGN.md` for visual decisions.
- Use `CONTENT.md` for editorial decisions.
- Inspect the repository to establish implementation facts.

Documentation describes intent but does not prove that a
feature exists or a requirement has been verified.

If a consequential conflict remains, explain it and ask.
Do not silently choose a new direction or rewrite the
documentation to justify your implementation.

## Core Priorities

### Clarity Over Flair

Prioritize readable content, clear hierarchy, and understandable
navigation over decorative effects.

Do not introduce interactions that make basic information
harder to find.

### Creativity Over Trend Following

Choose patterns because they suit the content and Dalton's
identity, not because they are fashionable.

Do not automatically add animated backgrounds, typing effects,
scroll-driven reveals, decorative terminals, or similar
portfolio conventions.

### Substance Over Self-Promotion

Let detailed work and authentic writing demonstrate capability.

Do not replace specific explanations with generic marketing copy.

### Personal and Professional Content Belong Together

Treat projects, research, blog posts, and poetry as intentional
parts of the same website.

Do not remove or minimize creative work merely to make the
site appear more professional.

## Establish Repository Facts First

Before editing:
1. Inspect the relevant files and configuration.
2. Identify existing patterns and reusable components.
3. Check the working tree for unrelated or uncommitted changes.
4. Identify the smallest change that satisfies the request.
5. Determine how the change can be verified.

Do not assume filenames, dependencies, installed extensions,
or configuration behavior solely from a design document.

Do not discard, overwrite, or revert unrelated user changes.

For substantial work, briefly state the intended approach
before making changes.

## Technical Foundation

The site uses Quarto.

The documented theme configuration is:

```yaml
theme:
  light: [flatly]
  dark: [darkly, assets/custom.scss]
```

The documented brand configuration is `brand/_brand.yml`.

Other documented styling files include:
- `assets/styles.css`
- `assets/listing-default.css`

Confirm the actual structure and configuration before editing.

### Implementation Approach

- Prefer existing Quarto capabilities and project conventions.
- Reuse existing styling and components before adding new ones.
- Keep changes scoped to the requested task.
- Avoid unnecessary JavaScript, dependencies, and abstractions.
- Do not migrate frameworks or replace the theme system
  without explicit approval.
- Do not edit generated output as a substitute for source changes.
- Follow the repository's existing policy for generated files.

Inspect configuration, scripts, and CI to find the supported
build and validation commands. Do not invent project commands.

## Design Boundaries

Preserve the established design direction unless the task
explicitly authorizes a change.

### Typography

The documented typefaces are:
- Raleway for headings.
- Nunito for body text.
- IBM Plex Mono for code.
- Georgia / Times New Roman for poetry.

Preserve intentional distinctions between content types.

Do not add fonts or substantially change typographic roles
without approval.

### Color and Appearance

Use the palette and mode-specific assignments in `DESIGN.md`
and the actual brand/style configuration.

Prefer existing design tokens and CSS variables over adding
duplicate hardcoded values.

Review visual changes in both light and dark appearances.

Do not assume that a color combination is accessible merely
because its colors are part of the approved palette.

### Notebook Character

"Poetry notebook" describes personal, reflective character.
It is not automatic permission to add paper textures,
handwriting fonts, simulated notebooks, or ornamental effects.

### Styling Scope

- Keep page-specific styles scoped to the relevant page or component.
- Put shared rules in the appropriate existing shared stylesheet.
- Avoid broad selectors that unintentionally affect other content.
- Avoid accumulating overrides where an existing rule can be
  corrected cleanly.
- Preserve intentional whitespace and line breaks in creative work.

## Content and Factual Integrity

Do not invent or embellish:
- Biographical facts.
- Credentials, affiliations, or positions.
- Publications, awards, or achievements.
- Project capabilities or performance measurements.
- Research results.
- Collaborators or contributions.
- Personal experiences, feelings, or opinions.
- Availability or response-time commitments.

Use confirmed information and existing approved content.

When information is missing, ask or use a clearly marked
draft placeholder. Do not publish unresolved placeholders.

Distinguish completed work from experiments, plans, and
work in progress.

### Voice

Use clear, personal language.

Avoid corporate phrasing, inflated claims, and generic
portfolio slogans.

Do not force every interest into a single professional narrative.

### Projects and Research

Preserve:
- The problem or question being addressed.
- Why it matters.
- Dalton's actual contribution.
- Technical and scientific nuance.
- Limitations and uncertainty.
- The distinction between preliminary and established findings.

Do not execute scientific examples or notebooks merely to
render a page if doing so could trigger expensive computation,
network requests, or changes to external systems. Inspect the
execution configuration first.

### Poetry and Personal Writing

Unless explicitly asked to edit the work:
- Preserve wording and meaning.
- Preserve punctuation and capitalization.
- Preserve line breaks, stanza boundaries, and intentional spacing.
- Do not add interpretations, summaries, or decorative quotations.
- Do not rewrite creative work to fit a layout.

If a rendering problem affects a poem, fix the presentation
or report the limitation rather than silently changing the poem.

## Navigation and Content Structure

Preserve clear routes to:
- Personal introduction and background.
- Projects and research.
- Blog posts and writing.
- Poetry.
- Résumé and academic CV.
- Contact information and relevant social profiles.

Follow the actual navigation configuration and approved sitemap.

Ask before making substantial changes to:
- Top-level navigation.
- Public page paths or slugs.
- Content categories.
- Homepage emphasis.
- The visibility of poetry or other major content areas.

If a requested change moves or removes a public page,
identify affected internal links and discuss redirects
where appropriate.

## Accessibility and Usability

Treat accessibility as a requirement, not a claim to repeat
without evidence.

For relevant changes:
- Use meaningful heading structure.
- Preserve keyboard navigation.
- Provide visible focus states.
- Use descriptive link and button labels.
- Provide appropriate text alternatives for meaningful images.
- Check text and interface contrast.
- Respect reduced-motion preferences when motion is introduced.
- Check small-screen layouts and content overflow.
- Ensure code and poetry remain usable without losing
  meaningful formatting.

Automated checks do not replace manual review.

Do not claim WCAG compliance or a passing accessibility audit
unless the relevant evaluation was actually performed and
its scope is stated.

## Extensions, Scripts, and External Services

Preserve existing extensions unless the task requires otherwise.

Ask before:
- Adding or removing dependencies or Quarto extensions.
- Adding analytics, tracking, embedded third-party services,
  or a contact-form backend.
- Introducing external scripts.
- Changing deployment or domain configuration.
- Changing licensing or attribution.

Never place secrets, tokens, or private information in source
files, rendered pages, or logs.

Do not modify third-party extension code as a shortcut unless
that approach is explicitly approved.

## Verification

Find and follow the repository's documented verification process.

For content changes:
- Render or preview the affected pages where feasible.
- Check links, images, metadata, and downloads.
- Confirm that no placeholders or unsupported claims were added.

For visual changes:
- Check light and dark appearances.
- Check narrow and wide viewports.
- Inspect headings, long text, code, and relevant creative content.
- Check hover and keyboard-focus states.
- Check for clipping, overflow, and unintended global changes.

For configuration or shared styling changes:
- Run the relevant site-wide build or checks where feasible.
- Inspect more than the page that motivated the change.

If a command fails, distinguish an implementation failure
from a pre-existing issue or environment limitation.

If browser inspection or another check is unavailable,
state that limitation. Do not report an unperformed check
as passing.

## Scope and Change Control

Make the smallest coherent change that fulfills the request.

Do not:
- Redesign unrelated pages.
- Rewrite unrelated content.
- Remove unfamiliar files without investigating their role.
- Change acceptance criteria to hide a failure.
- Suppress warnings without understanding their cause.
- Commit, push, deploy, or publish unless explicitly authorized.
- Perform destructive repository operations without approval.

Update related documentation when behavior or design decisions
change, but do not redefine the site's vision on your own.

## Completion Report

At the end of a task, briefly report:
- What changed and why.
- Which files or areas were affected.
- What checks were performed and their results.
- What could not be verified.
- Any remaining issue or decision requiring Dalton's input.

Separate completed work from recommendations and future ideas.