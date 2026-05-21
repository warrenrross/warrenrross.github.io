# ADR 0001 — Hand-written HTML, no build step

**Status:** Accepted — 2026-05-20

## Context
The site is being redesigned from a 2019 HTML5 UP template ("Read Only") to a modern personal site. The redesign needs to:
- Ship on GitHub Pages from `warrenrross.github.io` (the user/org page repo)
- Position Warren as a career tech professional with a Data Science focus
- Be maintainable by a single person (Warren) who edits it a handful of times per year
- Total scope is roughly 2–3 pages (home, bio, possibly a longer projects/timeline page)

Three stacks were genuinely considered:
1. **Hand-written HTML + modern CSS, no build step.**
2. **Static site generator** (Jekyll has native GH Pages support; Astro / Eleventy would need a GH Actions workflow).
3. **Modern JS framework** (Next.js, SvelteKit) served as a static export.

## Decision
Use **hand-written HTML + modern CSS, no build step.** The repo serves `.html` and `.css` files directly from the root via GitHub Pages.

## Consequences

**Positive**
- Zero toolchain to maintain. Edits to copy or links are one-file changes.
- Nothing to break in 2027 when a Node version, an Astro version, or a Jekyll Ruby gem drifts.
- GitHub Pages serves it natively with no config and no Actions workflow.
- The mental model for future-Warren editing the site is "open the file in any editor." Onboarding cost = zero.

**Negative**
- No templating: if multiple pages share a header/nav, changes have to be duplicated by hand. Mitigated by keeping the page count small (≤3) and using one shared CSS file.
- No Markdown authoring; long-form content is authored as HTML or hosted on Medium and linked.
- If the site grows to a blog or many project pages later, this decision will need to be revisited (likely toward Jekyll, since GH Pages already supports it natively).

**Rejected alternatives**
- *Jekyll / Astro / Eleventy* — real templating, but the build step and config burden outweigh the benefit at 2–3 pages.
- *Next.js / SvelteKit* — overkill. Maintaining a Node toolchain to ship mostly-static content is a long-term liability for a personal site touched a few times a year.
