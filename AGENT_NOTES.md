# Agent notes

Context for anyone (or any agent) opening this repo for the first time. The README is for visitors; this file is for the people doing the work.

## What this repo is

The source of [warrenrross.github.io](https://warrenrross.github.io/). Hand-written HTML and CSS, no build step, served from GitHub Pages on the `master` branch.

## Where to look for things

| Looking for | File |
| --- | --- |
| Canonical names, audience, what we're saying and not saying | [`CONTEXT.md`](./CONTEXT.md) |
| Decisions we don't want to re-litigate every time | [`docs/adr/`](./docs/adr/) |
| The site itself | [`index.html`](./index.html), [`assets/`](./assets/) |
| Long-form bio copy | [`bio/`](./bio/) |
| Photos used on the page | [`images/`](./images/) |

`CONTEXT.md` is a glossary, not a spec. If you add a new term — a section name, a positioning pillar, a project pair — define it there so the next round of edits uses the same words.

## Architecture decision records

ADRs in `docs/adr/` cover decisions that are hard to reverse or surprising on first read. Index:

- **0001** — Hand-written HTML, no build step. Why this site isn't a Next.js app.
- **0002** — Two sibling browser-only hand-classifier repos. Why `Hand_AI` and `JS-Image-Classifier` exist as separate repos with different goals.
- **0003** — Water → sky → data metaphor. Why the page is structured around this image and what art belongs where.

When a decision feels like a real trade-off — one you'd want to explain to your future self — write a new ADR. Skip the ADR for cosmetic edits and small content tweaks.

## Sibling repos that depend on this one

These repos are linked from the site and reference ADRs here:

- [`warrenrross/Hand_AI`](https://github.com/warrenrross/Hand_AI) — browser-only gesture sticker board. Points to ADR-0002.
- [`warrenrross/JS-Image-Classifier`](https://github.com/warrenrross/JS-Image-Classifier) — train-your-own webcam classifier (Rock-Paper-Scissors). Points to ADR-0002.
- [`warrenrross/live-quakes`](https://github.com/warrenrross/live-quakes) — Leaflet earthquake map.

If you change an ADR linked from one of these repos, also push a note over there so the cross-link still makes sense.

## House style

- Plain HTML, semantic tags, low-JS. No frameworks, no bundler.
- Copy is written for recruiters and technical peers reading in 2026. Anything that sounds like 2019 bootcamp self-talk gets cut.
- Project cards link to a live demo first, code second. If a project has no live demo, the code link is fine on its own.
- Photos go through the water → sky → data narrative on the home page. New photos that don't fit that arc belong in `bio/` or a dedicated page, not the hero.
