# CONTEXT — warrenrross.github.io

> Glossary of canonical terms for this site. Not a spec, not a scratchpad — just the language we've agreed on.

## Site purpose
**Personal site of Warren Ross.** Positions Warren as a **career tech professional** with a Data Science focus. Audience is recruiters, hiring managers, and technical collaborators evaluating Warren in 2026.

## Audience
- **Primary:** Recruiters and hiring managers in data / tech roles
- **Secondary:** Technical collaborators and peers
- **Not the audience:** 2019-era bootcamp peers, casual social-media followers

## Positioning pillars
- **Lead with Data Science.** DevOps drops back; not erased but no longer co-equal in the tagline.
- **De-emphasize (do not erase) USC bootcamp.** It's history, not headline. May appear deep in a timeline / education section, not in the hero.
- **Career tech professional, not career-pivoter.** Copy written in 2019 ("I'm pivoting", "rebooted with a bootcamp") is stale and must be retired.
- **Align with LinkedIn.** Site copy and timeline should not contradict [linkedin.com/in/warrenrross](https://www.linkedin.com/in/warrenrross/).

## Signature visual — "Journey triptych" (water → sky → data)
The triptych encodes a literal vertical climb: **out of the ocean, through the sky, into data science.** This is the spine of the whole site — palette, copy, and section order all flow from this metaphor.

Panels, left → right:
1. **Water** — Navy diver / Pearl Harbor era. *Photo TBD; left as a deliberate empty slot in v1 with a clear placeholder.*
2. **Sky** — the leap, the transition. `images/avatar.png` (the existing in-air skydiving photo).
3. **Data** — ashore, doing the work today. `images/headshot.jpg`.

These three are *one composition*, not three separate decorations. The `evolution-man-to-machine` image is **retired** — it was a generic before/after gag and doesn't fit the climb metaphor.

**v1 ship state:** Two-panel composition (sky + data) with the left panel reserved as a labeled placeholder. Adding the water photo later is a one-line swap.

## Featured long-form post
**"Best Kombucha Tutorial Ever"** ([Medium, Jul 3, 2021](https://medium.com/@warrenrross/best-kombucha-tutorial-ever-839739ac72f0)).
Replaces the previously embedded "Hero or Zero: What's to become of Siraj?" tweet as the featured personal-writing item.

## Stack
**Hand-written HTML + modern CSS, no build step.** Site is plain `.html` files (and `.css`) served directly by GitHub Pages from the repo root. No Jekyll, no Astro, no Node toolchain. See [ADR-0001](docs/adr/0001-hand-written-html-no-build-step.md).

## Information architecture
**Single-page scrolling site.** All content lives on `index.html`. The legacy `/bio/` page is retired; its content folds into an About / Journey section on the home page. Canonical section order:

1. **Hero** — name, current positioning line, the Journey triptych
2. **About / Journey** — long-form bio narrative (military → pivot → career tech professional), aligned with LinkedIn
3. **Selected Work** — hand-curated portfolio cards (not every repo)
4. **Writing** — featured: kombucha Medium article; room for more later
5. **Connect** — LinkedIn, GitHub, Medium, X, Dev.to, Instagram

Navigation is anchor links (`#about`, `#work`, `#writing`, `#connect`) that scroll within the page.

## Terminology
- **"X"** — the platform formerly known as Twitter. All visible labels, icon classes, and aria-labels must say "X" (not "Twitter"). URLs to `twitter.com/warrenrross` should be updated to `x.com/warrenrross`.
- **"Portfolio"** — projects Warren has shipped and wants to be evaluated on. Distinct from coursework.
- **"Coursework"** — USC bootcamp homework repos (`USC_Homework-*`, `USCbootcampHomeWork1`, `USCBootcampHomework2`). NOT the same as Portfolio.
- **"Journey"** — the visual + narrative arc from military → pivot → career tech professional. Used in the hero section.

## Selected Work — curation
**Hand-curated, not exhaustive.** Coursework repos are excluded by definition. **Canonical card order** (top → bottom on the page): Bean to Brew → Grounds for Correlation → live-quakes → RPS vs the Browser → Hand_AI → JabberJuicy.

| Tier | Project | Repo | Notes |
|---|---|---|---|
| Hero | **Bean to Brew** | [warrenrross/Bean_to_Brew](https://github.com/warrenrross/Bean_to_Brew) | Top of Selected Work. Eventually folds in `World_Coffee_Trade`. |
| Highlight | **Grounds for Correlation** | [warrenrross/coffee_bean_production_analysis](https://github.com/warrenrross/coffee_bean_production_analysis) | Statistical analysis, live Marimo notebook. |
| Refurbish | **live-quakes** (refurbished earthquake map) | [warrenrross/live-quakes](https://github.com/warrenrross/live-quakes) (rename of `USC_Homework-14_GeoMapping`) | See “Earthquake refurbish” below. |
| Sibling pair | **RPS vs the Browser** + **Hand_AI (browser-only)** | [JS-Image-Classifier](https://github.com/warrenrross/JS-Image-Classifier) + [Hand_AI](https://github.com/warrenrross/Hand_AI) | Two browser-only siblings sharing a common ML core. See “Hand-classifier projects” below. |
| Range proof | **JabberJuicy** | [warrenrross/jabberjuicy](https://github.com/warrenrross/jabberjuicy) | Live at [jabberjuicy.com](https://jabberjuicy.com). Placed last; framed as “full-stack range.” Team project (C#/.NET + SQL Server). |

## Hand-classifier projects (two sibling repos)
Both projects share the same technical core — webcam → in-browser hand-gesture model (MediaPipe Hand Landmarker or TensorFlow.js equivalent) → classification → interaction. They differ in what the classification *drives*. See [ADR-0002](docs/adr/0002-two-sibling-hand-classifier-repos.md).

| Repo | New framing | What it does |
|---|---|---|
| [warrenrross/JS-Image-Classifier](https://github.com/warrenrross/JS-Image-Classifier) | **Rock-Paper-Scissors vs the Browser** | Train the classifier on your own webcam captures, then play RPS rounds against it. Finishes the original “gamify it” intent that was never completed. |
| [warrenrross/Hand_AI](https://github.com/warrenrross/Hand_AI) | **Open-ended in-browser hand classifier** | Capture your own classes and probe the model. Move off the FastAPI backend to a fully in-browser, edge-capable model. |

**Both must be browser-only** (no backend) so they can ship as static demos on GitHub Pages with zero hosting cost.

They appear side-by-side in Selected Work as siblings demonstrating the same capability in two different use cases.

## Earthquake refurbish (`live-quakes`)
- **Rename in place** on GitHub: `USC_Homework-14_GeoMapping` → `live-quakes`. GH redirects old URLs automatically.
- **Visual goal:** “Google-Maps-style look, free stack.” Keep Leaflet; swap basemap to a muted modern tile provider (Carto Voyager / Stadia Alidade Smooth / MapTiler) requiring no API key. Refresh markers + popups to feel like Google’s info cards.
- **Retire** the Mapbox token requirement in `static/js/config.js`. No API keys on a public personal-portfolio demo.
- **Strip USC / Trilogy / bootcamp branding** from README and on-page content. The fact that this started as coursework is not part of the story we’re telling.
- Keep the timeline plugin feature — it’s the standout interaction.

## Current education / role (RESOLVED)
Warren is an **undergraduate Data Science student at the University of Arkansas**, currently working toward the degree (and a graduate degree thereafter). The UArk Data Science program is **interdisciplinary across three colleges** (Business, Science, Engineering) and **instructs students to list the program under LinkedIn “Experience”** (not “Education”) because the program treats the student experience like work experience. That LinkedIn quirk is the source of the apparent contradiction — it does **not** mean Warren is employed there.

The site copy should say *“Undergraduate Data Science student, University of Arkansas”* and not draw attention to the LinkedIn-categorization quirk.

## Terminology (additions)
- **“UArk Data Science program”** — the interdisciplinary undergraduate program at the University of Arkansas spanning Business, Science, and Engineering colleges. Where Warren is currently a student.

## Visual direction
**Sky and water blue theme**, anchored in the water → sky → data metaphor. Personal, not corporate.

- **Palette (proposed):**
  - Deep ocean blue — navigational anchor, headings, footer
  - Sky blue — backgrounds, light surfaces
  - Sand / warm cream — the “shore arrival” accent. Pairs with the headshot’s warm-neutral backdrop.
  - Charcoal — body text
  - White — page background
- **Type:** Clean modern sans for body. A character-ful serif (or a strong geometric sans) for headings — finalized in implementation.
- **Layout:** Generous whitespace, content-led. Not a dark dashboard, not a corporate-blue page.

## Open questions
*(none blocking the initial build. Future: Navy/diver photo for panel 1; alternate skydiving / dive-team photos if Warren has them.)*
