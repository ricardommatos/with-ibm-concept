# WITH — IBM · concept demo

Interactive logo composition exploring the **WITH IBM** mark.

## Live demos

- **v1** — geometric variants (thin, capsule with media, circles, waveform): [ricardommatos.github.io/with-ibm-concept](https://ricardommatos.github.io/with-ibm-concept/)
- **v2** — brand-story variants (forest, pulse, helix, constellation) with matching captions: [ricardommatos.github.io/with-ibm-concept/v2.html](https://ricardommatos.github.io/with-ibm-concept/v2.html)
- **v3** — Three.js variants (boost, blaze, build, invent) with brand-verb captions: [ricardommatos.github.io/with-ibm-concept/v3.html](https://ricardommatos.github.io/with-ibm-concept/v3.html)

## How to use

Drag the IBM logo to the right. Past ~50% the cluster locks at the final state and a 5-second auto-reset countdown begins. Three reset paths: click the ↺ button, wait 5s, or click outside the animation area.

### v1 features

- Four random middle-mark variants (thin / capsule / circles / waveform)
- Capsule variant accepts up to 10 uploaded images or videos, picked randomly per drag
- **Hand mode** (✋) — pinch (thumb + index) to grab, horizontal motion drives the drag, via MediaPipe Hand Landmarker

### v2 features

Same interaction model. Four conceptual variants tied to IBM client stories:

- **forest** — *Planting 15 billion trees with IBM* (NASA)
- **pulse** — *Protecting vulnerable patients with IBM* (Mass General Brigham)
- **helix** — *Discovering the next medical miracle with IBM* (Moderna)
- **constellation** — *Pinpointing critical food aid with IBM* (UN World Food Programme)

Caption swaps in sync with the variant.

### v3 features

Three.js scene rendered in a canvas behind the SVG. Four 3D effects tied to IBM brand verbs:

- **boost** — marching-cubes metaballs that morph and orbit
- **blaze** — particle storm exploding outward
- **build** — instanced cube cluster assembling
- **invent** — displaced sphere with simplex-noise vertex shader

## Stack

Pure HTML + SVG + JS, no build step. v3 lazy-loads `three@0.160.0` from jsDelivr via importmap. MediaPipe Tasks Vision lazy-loaded only when hand mode is activated.
