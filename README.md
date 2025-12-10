# MapLibre 3D Taiwan Map

A 3D interactive map of Taiwan built with MapLibre GL JS, featuring interactive county and district visualization with zoom-based layer management.

## Features

- 🗺️ **3D Building Visualization**: Display 3D buildings at zoom level 13 and above
- 🏛️ **County Boundaries**: Interactive county boundaries visible up to zoom level 13
- 🏘️ **District Boundaries**: Clickable districts with detailed view, hidden at zoom level 14+
- 🎨 **Hover Effects**: Visual feedback when hovering over counties and districts
- 🎯 **Navigation**: Quick access buttons for Taipei 101 and full Taiwan view
- ⌨️ **3D Controls**: Right-click drag or Ctrl+Click to tilt and rotate the map

## Project Structure

```
├── index.html          # Main map application (uses original data)
├── demo.html           # Demo version (uses simplified data)
├── simplified/         # Compressed GeoJSON data
│   ├── index.json      # County-to-filename mapping
│   ├── twCounty2010.geo.json
│   └── [county-*.geo.json files]
└── original/           # Full GeoJSON data (optional)
```

## Usage

### Local Development

Serve the files locally:

```bash
python3 -m http.server 8000
# or
npx serve
```

Then open `http://localhost:8000/index.html` in your browser.

### Files

- **index.html**: Uses original (full-resolution) GeoJSON data
- **demo.html**: Uses simplified (compressed) GeoJSON data for faster loading

## Controls

- **Mouse Wheel**: Zoom in/out
- **Right-Click Drag**: Tilt and rotate the map
- **Ctrl + Left-Click Drag**: Alternative tilt and rotate
- **Click on County**: Zoom into county and view districts
- **Click on District**: Zoom into district details
- **Click outside**: Return to county view

## Data

The map uses:

- [OpenStreetMap](https://www.openstreetmap.org/) via OpenFreeMap Liberty style
- Taiwan administrative boundary GeoJSON files (simplified and original versions)
- County and district boundaries in `twCounty2010.geo.json` format

## Zoom Levels

- **Zoom < 13**: County boundaries visible, districts hidden
- **Zoom 13-14**: Both county and district boundaries visible
- **Zoom ≥ 14**: Only district boundaries visible, 3D buildings prominent

## Dependencies

- [MapLibre GL JS](https://maplibre.org/) v3.6.2
- [Tailwind CSS](https://tailwindcss.com/) for UI styling

## Browser Compatibility

Works on all modern browsers that support WebGL and ES6 JavaScript.
