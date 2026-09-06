# Human Atlas Organs combined organ explorer

**[Live preview →](https://human-altas-organs.vercel.app)**

![Human Atlas interface showing the full body view with body systems and layer controls](screenshot.png)

Full editable HTML, CSS, JavaScript, Three.js and local anatomy data.

Run from this folder:

```sh
python3 -m http.server 8000 --directory dist
```

Open http://localhost:8000. Open this folder in Codex or VS Code to edit it. No build step, npm install or API key is required. Use HTTP, not file://. A modern browser with WebGL, import maps and DecompressionStream is required.

## Category views

Full body (2,234 meshes), heart (93), brain (59), kidneys (2), lungs (280), liver (60), stomach (1), pancreas (4), spleen (1). Organ categories follow named source concepts, while the heart uses the focused Heart Atlas selection. Category counts are modeled pieces, not counts of distinct organs.

Each view supports camera rotation, zoom, front/back/side views, search within the category, layer visibility, selection, isolation and exploded layout. Heart also has chamber, valve, wall and vessel layers plus Reveal inside. Small organs may only have one mesh; this data does not provide detailed internal kidney anatomy.

## Files

- dist/index.html: interface and content
- dist/style.css: responsive styling
- dist/app.js: viewer and category interactions
- dist/categories.json: category membership and heart layer mappings
- dist/models/atlas.json: full structure catalogue and geometry offsets
- dist/models/body-\*.bin.gz: local anatomical geometry
- dist/three.js and dist/orbit.js: Three.js dependencies
- dist/favicon.svg, dist/favicon-32.png, dist/apple-touch-icon.png: browser tab and home-screen icons

Upload dist contents to any compatible static host. Fonts use an optional external Google Fonts stylesheet with local fallbacks.

## Attribution and scope

Copyright (c) 2026 Louis Yoong. The interface code in this repository is licensed under MIT — see [LICENSE](LICENSE).

BodyParts3D, copyright The Database Center for Life Science, licensed CC Attribution 4.0 International: https://dbarchive.biosciencedbc.jp/en/bodyparts3d/lic.html
Three.js and OrbitControls are MIT licensed; retain their notices.

Adult male reference anatomy. Chamber cavities are rendered as solid volumes; colors and exploded positions support exploration and do not simulate physiology. This dataset does not represent all anatomy or variation. Educational use, not diagnosis or surgical planning.

JavaScript syntax, category references, heart mappings and control IDs were checked. Existing geometry byte lengths and offsets were previously verified. Browser interaction testing has not been performed.

## Redesigned interface

Dark charcoal viewer, cyan controls, horizontal organ categories, right-side layer inspector and condensed display typography. Responsive mobile layout places the viewer before layer controls. Anatomy and category functionality are preserved.
