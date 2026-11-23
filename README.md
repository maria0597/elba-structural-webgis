# Elba Structural WebGIS

An interactive, mobile-first WebGIS and 3D terrain viewer built to document 20 key geological outcrops across Elba Island (Northern Tyrrhenian Sea, Italy). Designed as a digital field companion, it combines a custom Leaflet StoryMap interface with a georeferenced structural map, a W–E cross-section viewer, and a WebGL 3D elevation model.

**Live Demo:** [affioramentielba.netlify.app](https://affioramentielba.netlify.app)

---

## Key Features

* **Mobile-First StoryMap Interface:** Custom bottom-sheet layout inspired by native mapping apps, featuring smooth camera fly-to animations and sequential navigation across all 20 field stops.
* **Thematic Filtering:** Filter outcrops dynamically across four main geological themes:
  * Subduction & Mélange
  * Extension & LANF (Zuccale Fault)
  * Magmatism
  * Mineralizations & Skarn
* **Georeferenced Geological Overlay:** Toggleable structural map of Elba Island (Complexes I–V, Monte Capanne and Porto Azzurro plutons, major thrusts and normal faults) georeferenced in QGIS and paired with a live opacity slider and interactive legend.
* **Geological Cross-Section Viewer:** Full-screen modal displaying the W–E structural cross-section across the Zuccale low-angle normal fault.
* **3D Terrain Exploration:** Integrated `Qgis2threejs` WebGL viewer allowing interactive 3D inspection of the island's topography and geology, with seamless 2D/3D switching.

---

## Tech Stack

* **GIS & Data Processing:** QGIS, GDAL (georeferencing & raster conversion), `qgis2web` (GeoJSON/JS data export), `Qgis2threejs` (3D WebGL scene).
* **Frontend:** Vanilla HTML5, CSS3 (responsive mobile layout), JavaScript (ES6).
* **Mapping:** Leaflet.js, Google Satellite basemap.
* **Deployment:** Netlify (continuous deployment via GitHub).

---

## Project Structure

```text
.
├── index.html                 # Main 2D StoryMap application (HTML/CSS/JS)
├── css/                       # Leaflet stylesheets
├── js/                        # Leaflet core libraries
├── data/
│   └── affioramenti_elba_3.js # GeoJSON dataset of the 20 outcrops
├── images/
│   ├── geologia_elba.png      # Georeferenced geological map overlay
│   └── sezione_elba.png       # W-E structural cross-section
├── foto/                      # Outcrop field photographs
└── 3d/
    └── index.html             # Qgis2threejs 3D terrain viewer
