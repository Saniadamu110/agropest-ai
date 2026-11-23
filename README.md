# AgroPest AI

AI-assisted pest identification and IPM (Integrated Pest Management) guidance for millet, sorghum and cowpea farmers in Yobe State, Nigeria.

**Live demo:** https://saniadamu110.github.io/agropest-ai/

---

## Overview

Smallholder farmers in Yobe State grow millet, sorghum and cowpea as staple crops, but pest outbreaks are often misdiagnosed or caught too late due to limited access to extension officers. AgroPest AI lets a farmer photograph an affected leaf, stem or pod and get back a likely pest match, a severity read, and an IPM-first treatment plan — in English or Hausa.

This repository currently holds a **working front-end prototype**, built to demonstrate the product concept and user flow ahead of institutional partnership and field data collection.

## How it works

1. **Select a crop** — millet, sorghum or cowpea.
2. **Upload a photo** of the affected plant part.
3. **On-device analysis** — the photo is processed entirely in the browser (nothing is uploaded to a server). The matching engine reads the image's colour distribution (healthy green vs. necrotic/brown tissue), dark-spot density (holes, frass, lesions), and edge/texture complexity.
4. **Match & recommend** — those features are compared against a small set of hand-authored pest signatures for the selected crop. The closest match is returned with a confidence score and a severity rating, followed by an IPM-first treatment plan.

### What this is — and isn't

The current matching engine is a **heuristic, rule-based prototype**, not a trained machine-learning model. It is useful for demonstrating the product flow and for early user feedback, but its diagnostic accuracy has not been validated against real field images. This is stated openly in the app itself. See [Roadmap](#roadmap) for the path to a production-grade computer vision model.

## Pest coverage (current prototype)

| Crop | Pests covered |
|---|---|
| Millet (Gero) | Downy mildew ("green ear"), millet head miner, stem borer |
| Sorghum (Dawa) | Shoot fly, sorghum midge, spotted stem borer |
| Cowpea (Wake) | Legume pod borer (*Maruca vitrata*), cowpea aphids, storage bruchids/weevils |

Each entry includes a short symptom description and a field-ready IPM treatment plan (cultural, biological/botanical, and chemical-last-resort practices), sourced from the project's Yobe/Borno bilingual IPM reference material.

## Bilingual support

The interface and treatment summaries are available in English and Hausa, toggled live without a page reload. Hausa phrasing is a first-pass working translation and is expected to be refined with input from local extension terminology.

## Tech stack

- Plain HTML, CSS and JavaScript — no build step, no external runtime dependencies
- Client-side image processing via the HTML5 Canvas API
- Hosted as a static site on GitHub Pages

Keeping the stack dependency-free was a deliberate choice: it keeps the demo lightweight, works offline after first load, and is easy for any contributor to read, audit and extend without a toolchain.

## Repository structure
