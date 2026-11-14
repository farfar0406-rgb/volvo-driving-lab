# Volvo Driving Lab — Multilingual Public Edition

Independent, unofficial interactive driving experience. This package contains the complete website for GitHub Pages.

Languages: `index.html` (繁體中文), `en.html` (English), `ko.html` (한국어). Use the top-right language selector to switch.

## File structure

```
index.html
 en.html
 ko.html
 game.js
 models/
   ES90_original.glb.gz
   EX60_uniform_rear_rims.glb.gz
   Low_Poly_Moose_Source.glb
 .nojekyll
 MOOSE_MODEL_CREDIT.txt
 DEPLOY_GUIDE_zh-TW.md
```

All three languages use **the same** `game.js` and `models/` directory. Keep the structure intact, and do not rename model files. Publish from the repository root using GitHub Pages (main / root). The website needs HTTP(S) to load model resources; opening HTML directly as `file://` may not work.

The game is an independent non-official simulation. Acceleration and safety-system behavior do not represent real-world vehicle operation. The moose mesh is attributed to Zafflex under CC BY 4.0; see `MOOSE_MODEL_CREDIT.txt`. Verify permissions for other 3D assets before publishing.
