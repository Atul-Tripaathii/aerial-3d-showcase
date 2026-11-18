# AeroVista 3D — project site

Static, browser-native showcase for an aerial 3D reconstruction project. It is packaged as an independent GitHub Pages site with a progressive Three.js viewer and an interactive method walkthrough.

| Path | What it is |
|---|---|
| `index.html` | Landing page |
| `architecture/` | Animated architecture walkthrough (single self-contained HTML file) |
| `viewer/` | Side-by-side 3D viewer: our reconstructions vs the native-4K reference, plus the input video |
| `poster/` | A1 poster (PDF and LaTeX source with figures) |

## Hosting with GitHub Pages

1. On GitHub, open **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to *Deploy from a branch*, branch `main`, folder `/ (root)`, and save.
3. After a minute the site is live at `https://<user>.github.io/aerial-3d-showcase/`.

The site has no build step. `.nojekyll` makes GitHub serve every file as is.

## Notes

- The 3D models are reduced web copies (about 20–35 MB each). The full-resolution combined model (112 MB) is left out because GitHub rejects files over 100 MB.
- All timings were measured on one GPU shared with another training job.
- F-scores are measured against the native-4K reconstruction at 1% of scene size, in the same camera frame.

Venkatasai Eswar Nandu · Atul Tripathi · M Rajvardhan · Atri Sukul (CS25M206) · Supervisor: Dr. Chalavadi Vishnu

## Independent project identity

This version uses the AeroVista 3D name and visual system. Its indigo/cyan interface is intentionally separate from the source showcase identity. Before publishing, replace any remaining institutional logos, author credits, PDFs, measurements, and model assets with material you are authorized to publish.

## Progressive 3D viewer

The landing page now contains the full project showcase and automatic progressive 3D loading. The previous landing page is preserved as `legacy-index.html`; `architecture/`, `viewer/` and `poster/` remain available. The revised poster linked by the new landing page is `assets/poster.pdf`, with a QR for this repository’s Pages address.

The campus model loads in 16 spatial pieces with four simultaneous requests and a shared preview/full-resolution texture. All 682,950 original web-mesh triangles and texture coordinates were verified unchanged. In a local simulated 8 Mbps / 60 ms connection, the first piece appeared at 6.3 s and loading completed at 27.3 s; production timing will vary. Failed transfers retry only missing pieces. The complete payload remains about 25 MB.

Expected URL after enabling Pages: https://atul-tripaathii.github.io/aerial-3d-showcase/

The primary showcase links `methods.html` for evaluation scopes. Historical comparison pages use their own protocols and are preserved separately.

## Architecture walkthrough

The main showcase and `assets/poster.pdf` show ADD, SWAP and KEEP gain equations with candidate/occupant definitions. The main architecture section embeds an animated walkthrough and links to its full-page view.
