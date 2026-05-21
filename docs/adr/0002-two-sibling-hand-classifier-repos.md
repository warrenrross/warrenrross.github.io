# ADR 0002 — Two sibling browser-only hand-classifier repos

**Status:** Accepted — 2026-05-20

## Context
Warren has two existing repos that occupy adjacent territory in browser ML:
- **JS-Image-Classifier** — 2019. TensorFlow.js transfer-learning demo. Was originally intended to gamify training a classifier (train, then play Rock-Paper-Scissors against it), but the game half was never finished.
- **Hand_AI / RPS.AI** — FastAPI backend + browser frontend. KNN classifier. Train-then-test loop. Strong architecture but the backend dependency means it can't ship as a zero-config public demo.

For the redesigned personal site, we need one or both of these to be *demoable from a link in the portfolio* with no hosting cost and no card-on-file. We also want to preserve the original "gamify it" intent of JS-Image-Classifier rather than dissolve it into a generic ML demo.

In-browser hand-gesture classification is now standard (2026): MediaPipe Hand Landmarker, TensorFlow.js, Teachable Machine models all run client-side with no backend. So the technical core of *both* projects can be the same code: webcam → in-browser hand model → classification → interaction. They only differ in what the classification drives.

Three options were considered:
1. **Fold into one repo** with two modes selectable on the page.
2. **Keep two sibling repos**, both browser-only, both shipped side-by-side on the portfolio.
3. **Platform / consumer split** — Hand_AI as a reusable library, JS-IC as a consumer of it.

## Decision
Keep **two sibling browser-only repos**:

| Repo | New framing | Drives the classification into… |
|---|---|---|
| `JS-Image-Classifier` | **Rock-Paper-Scissors vs the Browser** | A finished game loop with rounds and a score |
| `Hand_AI` | **Open-ended in-browser hand classifier** | A capture-your-own-classes / probe-the-model UI |

Both repos must be **browser-only** (no backend). The FastAPI backend in `Hand_AI` is retired.

## Consequences

**Positive**
- Each repo tells a focused, one-sentence story. Side-by-side on the portfolio they demonstrate "same capability, two use cases" — a stronger signal than one larger jack-of-both.
- Preserves the original "gamify it" intent of JS-Image-Classifier.
- Both ship as static GitHub Pages demos. Zero hosting cost. Zero card-on-file.
- Removes the "you need to run the backend to try it" friction that currently makes Hand_AI un-demoable from a portfolio link.

**Negative**
- Shared ML/webcam plumbing has to be maintained twice (or vendored). Mitigation: it's a small JS module — copy it, or publish it as a one-file ESM on jsDelivr later if drift becomes painful.
- Two repos = two READMEs, two deploys, two surfaces to keep current.

**Rejected alternatives**
- *One repo with mode switcher* — loses the "two distinct use cases" framing; harder to link from a portfolio as two separate demos with two clear stories.
- *Platform / consumer split* — over-engineered for a personal-portfolio scale; introduces an internal API contract to maintain for no external user.

## Follow-up work
- Retire the FastAPI backend in `Hand_AI`. Strip `backend/` directory; rewrite README around the browser-only flow.
- Pick a hand-landmark model (likely MediaPipe Hand Landmarker; TF.js fallback considered).
- Finish the RPS game loop in `JS-Image-Classifier` and drop the HTML5 UP template scaffolding from the 2019 build.
- Drop both Siraj-tutorial and HTML5 UP credits from JS-Image-Classifier README.
