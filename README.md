# WITH — IBM · concept demo

Interactive logo composition exploring the **WITH IBM** mark.

## Live demos

- **v1** — geometric variants (thin, capsule with media, circles, waveform): [ricardommatos.github.io/with-ibm-concept](https://ricardommatos.github.io/with-ibm-concept/)
- **v2** — brand-story variants (forest, pulse, helix, constellation): [v2.html](https://ricardommatos.github.io/with-ibm-concept/v2.html)
- **v3** — Three.js generative variants (flow, bloom, attract, weave): [v3.html](https://ricardommatos.github.io/with-ibm-concept/v3.html)
- **v4** — openprocessing-style art (stipple, ribbons, growth, ink): [v4.html](https://ricardommatos.github.io/with-ibm-concept/v4.html)
- **v5** — voxel physics (drop, rise, swarm), Codrops Pixel Voxel Drop: [v5.html](https://ricardommatos.github.io/with-ibm-concept/v5.html)
- **v6** — GPU shaders (rotate, droplets), Codrops Rotating Slideshow + interactive-droplets: [v6.html](https://ricardommatos.github.io/with-ibm-concept/v6.html)
- **halftone** — small standalone studio: rebuild a photo as a grid of stamped SVG patterns: [halftone.html](https://ricardommatos.github.io/with-ibm-concept/halftone.html)

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

- **stipple** — *Maximize every insight* — particles depositing dots into a long-lived buffer with age decay
- **ribbons** — *Modernize every flow* — five layered quadratic bezier ribbons in additive blend
- **growth** — *Innovate without limits* — differential growth simulation: chain repulsion + attraction + dynamic resampling
- **ink** — *Create what's never been* — calligraphic strokes built from quadratic beziers as triangle strips

### v5 features

Voxel physics, inspired by [Codrops Pixel Voxel Drop](https://tympanus.net/Tutorials/PixelVoxelDrop/) ([repo](https://github.com/1kkaku-KJ/Codrops-Pixel-Voxel-Drop)):

- **drop** — *Build block by block* — voxels rain with gravity and pile up on a virtual floor
- **rise** — *Scale new heights* — anti-gravity, voxels float toward a ceiling
- **swarm** — *Crush every limit* — damped-spring radial burst with rotational angular velocity

### v6 features

GPU shader effects:

- **rotate** — *Innovate every angle* — vertex shader port of the [Codrops Rotating Slideshow](https://tympanus.net/Tutorials/RotatingSlideshow/) ([repo](https://github.com/oluwadareseyi/webgl-rotating-image-gallery)): a textured plane that twists around its horizontal axis as drag advances. Each vertex's rotation angle = `dot(distortionAxis, position) * uDistortion`, easing with `qinticInOut`. Texture is a procedural canvas with IBM-blue + white stripes (echoing the IBM logo bars).
- **droplets** — *Connect every droplet* — fragment shader port of [koji014/interactive-droplets](https://github.com/koji014/interactive-droplets): raymarched SDF metaballs combined via smoothMin, fed a 15-position trail. As drag grows the trail head sweeps right, droplets stretch, smaller balls trail behind, iridescent shimmer from `noise3D(reflectDir + uTime)`.

### halftone

Standalone tool — not part of the v1–v6 drag composition. Upload a photo + a stamp SVG (defaults to a circle); the app rebuilds the photo as a grid of stamped pattern instances sized by per-cell luminance. Sliders for density, stamp size, gamma, min size; toggles for dark/light brightness mapping, stamp colour (white/black) and background (IBM blue/white/black). Export to PNG. The SVG is recoloured client-side via DOMParser before each render. Inspired by the dotted-portrait halftone aesthetic — and patterns sized to IBM-bar-like proportions are fair game.

## Stack

Pure HTML + SVG + JS, no build step. v3+ lazy-load `three@0.160.0` (with `ImprovedNoise` from `three/addons/math` for v3/v4) via importmap. MediaPipe Tasks Vision lazy-loaded only when hand mode is activated.
