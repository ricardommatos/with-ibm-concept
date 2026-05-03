# WITH — IBM · concept demo

Interactive logo composition exploring the **WITH IBM** mark.

## Live demos

- **v1** — geometric variants (thin, capsule with media, circles, waveform): [ricardommatos.github.io/with-ibm-concept](https://ricardommatos.github.io/with-ibm-concept/)
- **v2** — brand-story variants (forest, pulse, helix, constellation): [v2.html](https://ricardommatos.github.io/with-ibm-concept/v2.html)
- **v3** — Three.js generative variants (flow, bloom, attract, weave): [v3.html](https://ricardommatos.github.io/with-ibm-concept/v3.html)
- **v4** — openprocessing-style art (stipple, ribbons, growth, ink): [v4.html](https://ricardommatos.github.io/with-ibm-concept/v4.html)
- **v5** — voxel physics (drop, rise, swarm), inspired by Codrops Pixel Voxel Drop: [v5.html](https://ricardommatos.github.io/with-ibm-concept/v5.html)

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

### v3 features

Three.js. Four generative-art effects:

- **flow** — *Automate every flow* — curl-noise particle flow field with trails
- **bloom** — *Innovate every season* — phyllotaxis (golden-angle) spiral
- **attract** — *Maximize every signal* — Lorenz strange attractor traced in 3D
- **weave** — *Manage every connection* — Truchet tile pattern

### v4 features

Openprocessing-style generative art:

- **stipple** — *Maximize every insight* — particles flowing on curl-noise depositing dots into a long-lived buffer with age decay
- **ribbons** — *Modernize every flow* — five layered quadratic bezier ribbons in additive blend
- **growth** — *Innovate without limits* — differential growth simulation: chain of points with mutual repulsion + chain attraction + dynamic resampling
- **ink** — *Create what's never been* — calligraphic strokes built from quadratic beziers extruded into triangle strips with sin-curve pressure taper

### v5 features

Voxel physics, inspired by [Codrops Pixel Voxel Drop](https://tympanus.net/Tutorials/PixelVoxelDrop/) ([repo](https://github.com/1kkaku-KJ/Codrops-Pixel-Voxel-Drop)). Each variant is an `InstancedMesh` of 210 voxels with hand-rolled per-cube physics (gravity, ground bounce, angular velocity).

- **drop** — *Build block by block* — voxels rain from grid positions, stagger left → right, pile up on virtual floor
- **rise** — *Scale new heights* — anti-gravity, bottom-up release, voxels float toward an invisible ceiling
- **swarm** — *Crush every limit* — damped-spring radial burst with seeded directions; voxels spin proportional to speed

## Stack

Pure HTML + SVG + JS, no build step. v3 + v4 + v5 lazy-load `three@0.160.0` (with `ImprovedNoise` from `three/addons/math` for v3/v4) via importmap. MediaPipe Tasks Vision lazy-loaded only when hand mode is activated.
