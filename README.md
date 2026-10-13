# Pelagic Whale Corridor Atlas

Interactive web map of blue and humpback whale migration corridors, overlaid with commercial shipping lanes, industrial fishing pressure and deep sea mining areas. It is a static site: plain HTML, CSS and JavaScript, with no build step and no server.

## Files

- `index.html` – the atlas
- `embed-builder.html` – a page that writes embed links and iframe code
- `js/` – application code and data (`data.js`, `geo.js`, `mining.js`, `mining-geo.js`, `app.js`)
- `css/`, `vendor/`, `land.geojson`, `favicon.svg` – styles, libraries, fonts and country borders

## Run locally

Open a terminal in this folder and run `python3 -m http.server 8000`, then visit http://localhost:8000. Opening `index.html` by double-click will not work, because the map loads `land.geojson` with a web request.

## Host on GitHub Pages

1. Create a new public repository on GitHub.
2. Upload every file in this folder, keeping the folder structure. Include the hidden file `.nojekyll`.
3. In the repository, go to Settings > Pages. Under Build and deployment, set Source to "Deploy from a branch", choose the `main` branch and the `/ (root)` folder, then Save.
4. After a minute or two the site is live at `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

## Embed in ArcGIS StoryMaps or another page

Use your GitHub Pages address with `?embed=1` for the compact view:

```
https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/index.html?embed=1
```

Optional parameters, combined with `&`:

| Parameter | Values |
|---|---|
| `region` | North Pacific, North Atlantic, South Pacific, South Atlantic, Indian Ocean, Southern Ocean |
| `month` | 1 to 12 |
| `panel` | `whale` or `mining` |
| `layers` | comma list of `blue,humpback,shipping,fishing,mining,waypoints,threats` |
| `theme` | `dark` or `light` |
| `sat` | `0` turns off satellite imagery |
| `open` | `watchlist` or `layers` |

Open `embed-builder.html` on your hosted site to build and preview links and iframe code.

## Data and credits

- Whale routes, pressure areas and mining areas are hand-drawn editorial sketches based on cited sources; they are not telemetry, AIS data, licence boundaries or a risk forecast. See "Data & methods" inside the app.
- Satellite imagery: Esri, Maxar, Earthstar Geographics, and the GIS User Community (Esri World Imagery). Review Esri's terms before commercial or high-traffic use.
- Libraries and assets: Leaflet, Lucide icons, Natural Earth country borders, Satoshi typeface (Fontshare). Check each project's license before redistributing.
- No license is set for the project's own code. Add a `LICENSE` file when you decide how others may reuse it.
