# 🇵🇭 Philippines Petroleum Downstream Infrastructure & Historical Typhoon Vulnerability Analysis

> **An Interactive Geospatial Decision-Support Platform for Energy Security and Infrastructure Resilience Assessment**  
> *Developed for the Oil and Gas Security Exercise (OGSE) Programme by the Asia Pacific Energy Research Centre (APERC) in technical collaboration with the Department of Energy – Oil Industry Management Bureau (DOE-OIMB), Republic of the Philippines.*

[![GitHub Pages Deployment](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-brightgreen?style=for-the-badge&logo=github)](https://<YOUR-GITHUB-USERNAME>.github.io/<YOUR-REPOSITORY-NAME>/)
[![Leaflet](https://img.shields.io/badge/Leaflet-v1.9.4-199900?style=for-the-badge&logo=leaflet&logoColor=white)](https://leafletjs.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla%20ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/)
[![Licence](https://img.shields.io/badge/Licence-MIT-blue?style=for-the-badge)](LICENSE)

---

## 📌 Executive Overview

Following the permanent closure and decommissioning of Pilipinas Shell's Tabangao refinery in August 2020 and its subsequent conversion into the **Shell Import Facility Tabangao (SHIFT)**, the downstream petroleum supply chain of the Philippines underwent a structural reconfiguration. The nation transitioned from a dual-refinery landscape to an import-reliant model anchored by a single domestic refining facility: Petron Corporation’s 180,000-barrel-per-day (180 kb/d) complex in Limay, Bataan.

Consequently, domestic fuel security increasingly depends on an interconnected network of deep-water marine import terminals, inter-island coastal barge corridors, and regional bulk storage depots. Given the geographic position of the Philippine archipelago within the Western Pacific Typhoon Belt, critical downstream energy logistics are perpetually exposed to severe weather disruptions.

This web-based geospatial analytical platform was developed to provide policy analysts, emergency response coordinators, and energy planners with an operational, data-grounded overview of:
1. The **spatial distribution and capacity hierarchy** of the country's 33 principal downstream petroleum facilities.
2. The **geospatial overlap and vulnerability footprint** across historical tracks of the **12 most destructive typhoons** recorded in modern Philippine history.
3. Rapid **regional aggregation** of volumetric storage via dynamic spatial polygon selection (*lasso* tool) for contingency and emergency supply modelling.
4. Presentation-ready **high-resolution graphic export** tailored for executive and ministerial-level briefings.

---

## 🚀 Live Demonstration

The production build of the platform is hosted on GitHub Pages:  
👉 **`https://<YOUR-GITHUB-USERNAME>.github.io/<YOUR-REPOSITORY-NAME>/`**

*(Please substitute `<YOUR-GITHUB-USERNAME>` and `<YOUR-REPOSITORY-NAME>` with your corresponding GitHub repository details upon publication).*

---

## 🌟 Key Functional Features

### 1. 🗺️ Multi-Layer Geospatial Mapping & Graduated Symbology
- **33 Georeferenced Strategic Assets:** Precise coordinate mapping covering the single operating refinery (Petron Bataan), primary marine import terminals, and vital secondary distribution depots across Luzon, Visayas, and Mindanao.
- **Official DOE-OIMB Colour Categorisation:**
  - 🟢 **Refinery:** Phosphorescent Green (`#00E676`)
  - 🔴 **Import Terminal:** Crimson Red (`#FF1744`)
  - 🔵 **Secondary Storage Depot:** Vibrant Blue (`#2979FF`)
- **Capacity-Graduated Bubble Scaling:** Marker radii are mathematically scaled to the square root of storage capacity in thousand barrels (MB), preserving visual balance across disparate volume orders:
  $$\text{radius} = \max\left(6, \sqrt{\text{cap}_{\text{MB}}} \times 0.42\right)$$
- **Rich Contextual Popups:** Clicking any asset reveals operational metadata, regional jurisdiction, primary operator, storage capacity in Megalitres (ML), Thousand Barrels (MB), and Million Barrels (MMB), as well as dedicated product streams handled (e.g. ULSD, Mogas, Jet A-1, Fuel Oil, LPG).

### 2. 🌀 Extreme Weather & Historical Typhoon Track Overlays
- **12 Catastrophic Typhoon Tracks:** Digitised vector pathways of the most devastating tropical cyclones in Philippine meteorological history (including Super Typhoon *Yolanda / Haiyan*, *Odette / Rai*, *Rolly / Goni*, *Pablo / Bopha*, and *Angela / Rosing*), sourced from PAGASA records and Typhoon2000 meteorological archives.
- **Spatial Vulnerability Visualisation:** Enables instantaneous evaluation of storm paths cutting across high-density petroleum logistics corridors (e.g. the Batangas maritime corridor, Subic Bay, and Northern Mindanao).
- **Cyclone Intelligence Windows:** Detailed tooltips provide landfall coordinates, maximum sustained 10-minute winds, peak gusts, and historical damage metrics.

### 3. 📐 Spatial Polygon Lasso Selection Tool
- Freehand interactive boundary drawing across the map canvas using `leaflet-lasso`.
- **Dynamic On-the-Fly Aggregation:**
  - Real-time summation of isolated storage volumes in Megalitres (ML) and Million Barrels (MMB).
  - Facility count breakdown categorised by operational typology (refineries, terminals, depots).
  - Synchronous table filtering and visual highlighting for selected asset subsets.
  - Dedicated floating analytical summary panel with an instantaneous reset option.

### 4. 📋 Synchronised Analytical Sidebar & Reactive Querying
- **Strict Capacity Hierarchy:** Facilities are catalogued in descending order of volumetric capacity (from the Bataan Refinery at 1,552 ML / 9,761 MB down to the Polloc Port Depot at 6.57 ML / 41 MB).
- **Bidirectional Event Synchronisation:**
  - Selecting an asset in the table triggers a smooth cinematic pan/zoom (`map.flyTo`) directly to the asset coordinate and initiates the popup.
  - Selecting an asset marker on the map automatically scrolls the sidebar to the corresponding record (`scrollIntoView`) and applies contextual highlighting.
- **Categorical & Free-Text Filtering:** Instant filtering switches (All, Refineries, Terminals, Depots) combined with a responsive multi-field search engine (matching facility name, operator, or province).

### 5. 📸 Presentation-Ready High-Definition PNG Export
- Integrated one-click snapshot generation engineered specifically for PowerPoint (PPT) slides, executive summaries, and cabinet briefs.
- Employs `html2canvas` client-side rasterisation with CORS-enabled tile management (CartoDB Voyager / Dark Matter) to prevent security-tainted canvas restrictions.
- Captures active map extent, custom selections, legends, graduation scales, and graphical overlays cleanly.

### 6. ⚡ Autonomous, Zero-Dependency Architecture
- Built purely with standard **HTML5, CSS3, and modern Vanilla ECMAScript (ES6+)**.
- Completely free of complex toolchains, package managers (`npm`/`yarn`), or reactive framework overheads (`React`, `Vue`, `Angular`).
- Production-grade CDN asset delivery:
  - [Leaflet v1.9.4](https://unpkg.com/leaflet@1.9.4/) (Geospatial engine)
  - [Leaflet-Lasso v2.2.13](https://unpkg.com/leaflet-lasso@2.2.13/) (Spatial drawing selection)
  - [html2canvas v1.4.1](https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/) (Vector & DOM rasterisation)

---

## 📊 Philippine Downstream Petroleum Matrix: Core Baseline

*Data consolidated in collaboration with DOE-OIMB and APERC research figures:*

| Parameter | Annual Volume (Megalitres, ML) | Annual Volume (Million Barrels, MMB) | Daily Flow Rate (kb/d) | National Share (%) |
| :--- | :---: | :---: | :---: | :---: |
| **National Finished Product Demand** | **28,645.52** | **180.17** | **493.62** | **100.00%** |
| • Automotive & Industrial Diesel Oil (ADO/IDO) | 12,097.40 | 76.09 | 208.47 | 42.23% |
| • Motor Gasoline (RON 91 / 95 / 97+) | 8,873.18 | 55.81 | 152.91 | 30.98% |
| • Liquefied Petroleum Gas (LPG) | 3,742.88 | 23.54 | 64.50 | 13.07% |
| • Commercial Aviation Fuel (Jet A-1 / Avturbo) | 2,713.98 | 17.07 | 46.77 | 9.47% |
| • Industrial Fuel Oil (IFO) & Bunker Fuel | 896.54 | 5.64 | 15.45 | 3.13% |
| • Kerosene & Specialised Solvents / Asphalts | 321.55 | 2.02 | 5.54 | 1.12% |

### Macro-Regional Demand Distribution
- **National Capital Region (NCR - Metro Manila):** 30.87% (8,843.23 ML/a — primary consumption centre)
- **North Luzon (Regions 1, 2, 3 & CAR):** 21.24% (6,083.24 ML/a)
- **South Luzon (Regions 4A, 4B & 5):** 17.80% (5,098.31 ML/a)
- **Mindanao Island Group (Regions 9, 10, 11, 12, 13 & BARMM):** 15.98% (4,578.96 ML/a)
- **Visayas Island Group (Regions 6, 7 & 8):** 14.11% (4,041.78 ML/a)

### Refining vs Import Balance
- **Petron Bataan Domestic Refining Output:** 9,036.88 ML/annum (~56.84 MMBbl; 155.74 kb/d, reflecting ~86.5% nameplate capacity utilisation).
- **Domestic Demand Coverage:** Refined domestic production supplies **34.86%** of aggregate fuel demand; the remaining **65.14%** is met via direct seaborne product tanker imports.

---

## 📂 Repository File Structure

```text
.
├── index.html                                  # Standalone production application (served via GitHub Pages)
├── README.md                                   # Comprehensive technical and project documentation
```

---

## 💻 Local Testing & Execution

Due to the zero-dependency architecture, running the application locally requires no compilation, installation of runtimes, or local web server configuration:

1. Clone or download the repository to your local workstation:
   ```bash
   git clone https://github.com/<YOUR-GITHUB-USERNAME>/<YOUR-REPOSITORY-NAME>.git
   ```
2. Navigate to the repository directory and open [`index.html`](index.html) directly in any modern web browser (Google Chrome, Microsoft Edge, Mozilla Firefox, or Apple Safari).
   > *Note: An active Internet connection is required during runtime to retrieve third-party CDN stylesheets/scripts (Leaflet, Leaflet-Lasso, html2canvas) and CartoDB base map tiles.*

---



## 📚 Data Attributions & Acknowledgements

- **Asia Pacific Energy Research Centre (APERC):** Project methodology, energy security frameworks, and Oil and Gas Security Exercise (OGSE) initiative coordination.
- **Department of Energy – Oil Industry Management Bureau (DOE-OIMB), Republic of the Philippines:** Official statistics on downstream fuel supply, storage terminal inventories, and facility georeferencing.
- **Typhoon2000.ph & PAGASA:** Meteorological archives, storm tracks, barometric readings, and damage assessments for catastrophic Philippine typhoons.
- **OpenStreetMap & CartoDB:** Open-access vector and raster cartographic basemaps.

---

## 📄 Licence

This project is licensed under the **MIT Licence**. Please refer to the [LICENSE](LICENSE) file for complete terms and copyright notifications.
