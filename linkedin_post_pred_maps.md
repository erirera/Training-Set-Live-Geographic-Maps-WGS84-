# LinkedIn Post — Prediction Set Live Geographic Maps

---

🗺️ **When Your Training Data Tells a Different Story on a Real Map**

I've been working with the **Swiss Jura Heavy Metals dataset** for spatial machine learning benchmarking — 259 training samples across 7 heavy metals. The numbers looked clean. The histograms looked reasonable.

Then I projected the data onto a **live topographic map**.

Using **Leaflet.js** and a WGS84 affine transformation anchored to the Swiss Jura region, I built a 7-panel geographic dashboard — one live map per metal, overlaid on real **CARTO Dark Matter** satellite topography.

Here's what genuinely surprised me:

📍 **The Cd and Pb hotspots align with specific valley corridors** — not random. Seeing them over real terrain immediately suggests hydrological transport as a likely secondary distribution mechanism, something a pure statistics table will never tell you.

🪨 **The Geological Filter Panel changed how I reason about the data.** I can now uncheck individual rock formations — ordered **youngest → oldest** following stratigraphic literature — and watch the concentration patterns reorganise in real time across all 7 maps simultaneously.

→ Isolate Quaternary deposits (~2.58 Ma): Cd and Zn concentrations visually spike — the youngest alluvial soils accumulate more recent anthropogenic contamination.
→ Switch to Argovian (~166 Ma, oldest): the distribution flattens, consistent with deeper geogenic background levels.

🔶 **The Combined Study Area Boundary** — a convex hull of all 359 points (prediction + validation) with a +500 m offset, shown as a dashed golden polygon — immediately contextualises the survey coverage against the surrounding landscape. No GIS files required; computed entirely in pure Python.

Built completely without a backend. One HTML file, Leaflet.js from CDN, raw data baked in. Open it offline and it works.

What geochemical insights have you found appear only by looking at real-world spatial context? 👇

#GeoAI #SpatialAnalysis #DataVisualization #MachineLearning #Leaflet #OpenStreetMap #Geochemistry #Python #DataScience
