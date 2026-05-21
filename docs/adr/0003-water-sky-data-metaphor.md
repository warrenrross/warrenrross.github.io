# ADR 0003 — "Water → Sky → Data" as the site's organizing metaphor

**Status:** Accepted — 2026-05-20

## Context
The redesigned site needs an organizing visual and narrative idea — something the hero, palette, copy, and section order can all hang off. Four directions were considered:

1. **Editorial / minimalist** — off-white, warm coffee-roast accent, content-led. Pairs naturally with the headshot.
2. **Dark dashboard / data-tool** — near-black, monospace accents. Strong identity, headshot would need adaptation.
3. **Warm-personal** — cream, two accents, playful illustration. Most distinctive, highest execution risk.
4. **Corporate blue / LinkedIn-clean** — recruiter-safe, underused-personality.

In conversation, Warren reframed his own arc as **"climbing out of the ocean and making my way into data science,"** anchored in two specific biographical facts: Navy diver in Pearl Harbor in the early 2000s, and skydiver. The triptych composition we had already planned (skydiving + pivot + headshot) snaps into a much sharper three-beat story under this framing: **water → sky → data.**

## Decision
Adopt **"water → sky → data"** as the site's organizing metaphor. Every major design choice flows from it:

- **Triptych composition** rebuilt around the three elements (not a generic before/after). v1 ships with sky + data; the water panel slot is reserved for a photo Warren will supply later.
- **Palette** is sky/water blues + a warm sand "shore arrival" accent (which also harmonizes with the headshot's warm-neutral backdrop). Not warm-only, not corporate-blue-only.
- **About / Journey copy** narrates the climb explicitly: ocean → sky → ashore.
- The previously-planned `evolution-man-to-machine` image is **retired** — generic gag, wrong metaphor.

## Consequences

**Positive**
- The site has a real, personal point of view. Not a generic data-portfolio template.
- Hero, palette, and copy all reinforce each other instead of being three independent design decisions.
- Headshot pairs well: blue tie literalizes the palette without forcing it, warm backdrop pairs with the sand accent.
- Differentiates Warren from peers — most data-science portfolios don't have a biographical metaphor at all.

**Negative**
- Triptych v1 ships at 2/3 strength (sky + data) until Warren provides a Navy/diver photo for the water panel. Mitigation: layout reserves the slot with an honest placeholder rather than hiding it.
- The metaphor is *personal* — if Warren's positioning shifts later (e.g. away from solo career-tech-professional toward a co-founder or consultancy story), the metaphor may need to evolve.
- Coffee/kombucha work doesn't get a palette nod — the visual story is biography, not subject-matter. Mitigation: project cards carry their own color/imagery; the page chrome stays blue/sand.

**Rejected alternatives**
- *Editorial / coffee-roast warm* — strong default, but would have meant the site looked like any other content-first portfolio with a beige palette. The personal metaphor wins.
- *Dark dashboard* — would have forced the headshot to be cropped/graded against it; trades personality for a tooling aesthetic that doesn't match Warren's actual work (which is largely web-presentable data viz, not infrastructure).
- *Corporate blue* — same color family on paper, but loaded with the wrong connotation (LinkedIn-style conservatism). Sky-and-water blue is biographical; corporate-blue is impersonal.
