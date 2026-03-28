# Jura Heavy Metals — Prediction Set Live Geographic Maps

## Overview

This dashboard (`index.html`) projects all 259 training-set sample locations from the Swiss Jura geochemical dataset onto **live OpenStreetMap topography** using **Leaflet.js** and a WGS84 affine coordinate transformation. It replaces abstract grid scatter plots with true geographic context, enabling spatial pattern recognition before model deployment.

## Contents of This Folder

| File | Purpose |
|---|---|
| `index.html` | Live geographic map dashboard (open in any browser) |
| `gen_pred_maps.py` | Python generator script — re-run to rebuild `index.html` |

> **Note:** The CSV source data lives in `../prediction set EDA/jura_prediction_set.csv`. The generator reads both the prediction and validation CSVs to compute the shared study boundary polygon.

## Dashboard Features

### 7-Map Grid Layout
Seven independent **Leaflet.js** maps — one per heavy metal (Cd, Cu, Pb, Co, Cr, Ni, Zn) — rendered side-by-side on a dark CARTO basemap. Each map:
- Colour-grades every sample point from **blue (low)** to **pink/red (high)** concentration
- Auto-zooms to the tight bounding box of the data on load
- Shows a **clickable popup** on each point with: Sample ID · Concentration (ppm) · Rock Type · Land Use · Grid coordinates

### Live Categorical Filter Panel
A persistent control bar above the maps provides instant filtering across **all 7 maps simultaneously**:

**Rock Type** (ordered youngest → oldest per stratigraphic literature, with age labels):
- Quaternary (~2.58 Ma) · Portlandian (~152 Ma) · Kimmeridgian (~157 Ma) · Sequanian (~163 Ma) · Argovian (~166 Ma)

**Land Use:**
- Forest · Pasture · Meadow · Tillage

Unchecking any category sets those sample markers to fully transparent across all maps instantly.

### Combined Study Area Boundary
A toggleable **dashed golden polygon** overlaid on every map defines the combined study footprint across both the prediction and validation datasets. The boundary is computed as a **convex hull of all 359 points**, with a **+500 m outward offset** from the outermost samples. Useful for contextualising the geographic scope of the survey against real terrain features.

## Coordinate Projection Method
The raw local grid coordinates (`X km`, `Y km`) are transformed to `WGS84 (Latitude, Longitude)` using an affine approximation anchored to the Swiss Jura region (origin: Lat 47.15°, Lon 6.85°). The 1°/111.32 km conversion factor is applied with a cosine correction for longitude at the study latitude.

## Navigation
- **← Back to EDA** — Returns to the statistical analysis dashboard (`../prediction set EDA/index.html`)
- **Validation Maps →** — Opens the equivalent live map dashboard for the 100-sample validation set
