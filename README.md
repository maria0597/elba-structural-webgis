# Elba Structural WebGIS

An interactive, mobile-first WebGIS and 3D terrain viewer built to document 20 key geological outcrops across Elba Island (Northern Tyrrhenian Sea, Italy). Designed as a digital field companion, it combines a custom Leaflet StoryMap interface with a georeferenced structural map, a W–E cross-section viewer, and a WebGL 3D elevation model.

**Live Demo:** [affioramentielba.netlify.app](https://affioramentielba.netlify.app)

---

## Key Features

- **Mobile-First StoryMap Interface:** Custom bottom-sheet layout inspired by native mapping apps, featuring smooth camera fly-to animations, sequential navigation across all 20 field stops, and **horizontal swipeable photo galleries** supporting multiple field shots per outcrop.
- **Thematic Filtering:** Filter outcrops dynamically across four main geological themes:
  - Subduction & Mélange
  - Extension & LANF (Zuccale Fault)
  - Magmatism
  - Mineralizations & Skarn
- **Georeferenced Geological Overlay:** Toggleable structural map of Elba Island (Complexes I–V, Monte Capanne and Porto Azzurro plutons, major thrusts and normal faults) aligned in QGIS using Thin Plate Spline (TPS) transformation and paired with a live opacity slider and interactive legend.
- **Geological Cross-Section Viewer:** Full-screen modal displaying the W–E structural cross-section across the Zuccale low-angle normal fault.
- **Interactive 3D Terrain Viewer:** Integrated `Qgis2threejs` WebGL scene featuring a clean, custom top-left HUD that mirrors the 2D interface, allowing users to inspect the island's topography and independently toggle the geological map and outcrop markers over the satellite DEM.

---

## How to Explore the WebApp

### 2D StoryMap Mode
1. **Browse Outcrops:** Tap any numbered marker on the map—or press the tour button—to open the bottom sheet with tectonic unit, lithology, structural notes, and field photos. Use the previous/next arrows to follow the 4-day field itinerary in order.
2. **Swipe Field Photos:** On stops with multiple images (e.g., Cavo, Crocette, Procchio, Rio Marina, Spiagge Nere), swipe horizontally on the photo strip to view outcrop overviews, structural close-ups, and sketches.
3. **Filter by Theme:** Use the thematic pills at the top to isolate specific geological processes (e.g., *Magmatism* or *Extension & LANF*).
4. **Overlay Geology & Cross-Section:** Toggle the georeferenced geological map on or off, adjust its transparency with the opacity slider to compare contacts with satellite imagery, and open the W–E structural cross-section modal for subsurface context.

### 3D Terrain Mode
1. **Switch to 3D:** Click the **3D** button from the 2D map to load the WebGL elevation model (opens cleanly on the satellite DEM).
2. **Navigate the Relief:** Drag to orbit, pinch or scroll to zoom, and right-click drag (or two-finger drag on mobile) to pan across Monte Capanne, the central sector, and Monte Calamita.
3. **Toggle Layers:** Use the top-left control bar to switch **Carta Geologica** and **Affioramenti** on or off directly over the 3D terrain, or click **← Mappa 2D** to return to the StoryMap.

---

## Tech Stack

- **GIS & Data Processing:** QGIS, GDAL (Thin Plate Spline georeferencing & raster conversion), `qgis2web` (GeoJSON/JS data export), `Qgis2threejs` (multi-material 3D WebGL scene).
- **Frontend:** Vanilla HTML5, CSS3 (responsive mobile layout, CSS scroll-snap galleries), JavaScript (ES6).
- **Mapping & 3D:** Leaflet.js, Three.js (via `Qgis2threejs`), Google Satellite basemap.
- **Deployment:** Netlify (continuous deployment via GitHub).

---

## Project Structure

```text
.
├── index.html                 # Main 2D StoryMap application (HTML/CSS/JS)
├── css/                       # Leaflet stylesheets
├── js/                        # Leaflet core libraries
├── data/
│   └── affioramenti_elba_3.js # GeoJSON dataset of the 20 outcrops (supports multi-photo lists)
├── images/
│   ├── geologia_elba.png      # TPS-georeferenced geological map overlay
│   └── sezione_elba.png       # W-E structural cross-section
├── foto/                      # Outcrop field photographs and structural close-ups
└── 3d/
    └── index.html             # Customized Qgis2threejs 3D terrain viewer with custom HUD
