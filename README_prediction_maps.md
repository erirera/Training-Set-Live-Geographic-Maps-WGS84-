# Geographic Maps Dashboard — Prediction Set (n=259)

This directory contains the **Geographic Map Viewer** (`prediction_maps.html`), engineered specifically for the 259-sample Swiss Jura Training subset. 

Instead of abstract X/Y scatter plots, this newly upgraded dashboard leverages **Leaflet.js** to project and overlay your raw spatial data entirely onto live OpenStreetMap Dark topological topography (WGS84). 

## 🗺️ Why a Live Map + Filter Dashboard?

Before training complex spatial algorithms (like GNNs or Kriging), a data scientist must understand visual spatial autocorrelation—how heavy metals cluster organically within real-world environments.

### Key Capabilities
1. **Real-World Coordinate Projection**: The old local mathematical grid (`X km`, `Y km`) is flawlessly mathematically projected onto actual Swiss lat/lon coordinates natively within your browser, allowing you to instantly compare Cobalt spikes with real-world valleys or local roadways. 
2. **7-Grid Architecture**: Instantly compare the unique geographic concentration distributions of Cd, Cu, Pb, Co, Cr, Ni, and Zn horizontally side-by-side using responsive auto-zooming bounds.
3. **Live Categorical Filtering**: A dedicated Control Switchboard sits atop the maps. With a simple click, you can instantly turn off points belonging to `Forests`, `Quaternary Rock`, or `Meadows` across all 7 maps simultaneously. This allows visual isolation of heavy metals specifically within localized rock formations!

## 🔗 Integrated Workflow

- Click any circle marker on the map to reveal its original `Sample ID`, exact Heavy Metal `ppm` concentration, `Rock Type`, and `Land Use` string.
- Click **"← Back to EDA"** to return automatically to your deep-dive statistics (histograms, counts, correlation matrices).
- Click **"Validation Maps →"** to instantly contrast the training density with your strictly designated 100-sample test set.
