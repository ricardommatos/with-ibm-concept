# WITH — IBM · concept demo

Interactive logo composition exploring the **WITH IBM** mark.

## Live demos

- **v1** — geometric variants (thin, capsule with media, circles, waveform): [ricardommatos.github.io/with-ibm-concept](https://ricardommatos.github.io/with-ibm-concept/)
- **v2** — brand-story variants (forest, pulse, helix, constellation) with matching captions: [ricardommatos.github.io/with-ibm-concept/v2.html](https://ricardommatos.github.io/with-ibm-concept/v2.html)

## How to use

Drag the IBM logo to the right. Past ~50% the cluster locks at the final state and a 5-second auto-reset countdown begins. Three reset paths: click the ↺ button, wait 5s, or click outside the animation area.

### v1 features

- Four random middle-mark variants (thin / capsule / circles / waveform)
- Capsule variant accepts up to 10 uploaded images or videos, picked randomly per drag
- **Hand mode** (✋) — pinch (thumb + index) to grab, horizontal motion drives the drag, via MediaPipe Hand Landmarker

### v2 features

Same interaction model. Four new conceptual variants tied to IBM client stories:

- **forest** — *Planting 15 billion trees with IBM* (NASA)
- **pulse** — *Protecting vulnerable patients with IBM* (Mass General Brigham)
- **helix** — *Discovering the next medical miracle with IBM* (Moderna)
- **constellation** — *Pinpointing critical food aid with IBM* (UN World Food Programme)

Caption swaps in sync with the variant.

## Stack

Pure HTML + SVG + JS, no build step. MediaPipe Tasks Vision is lazy-loaded from CDN only when hand mode is activated.
