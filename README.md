# GeoMundus Conference – 18th Edition

## Geospatial Intelligence for Disaster Resilience

**From Data to Action: Mapping Risk, Strengthening Response and Building Safer Communities**

📅 **Date:** 16–17 October 2026  
📍 **Location:** Castellón de la Plana, Spain

---

### Workshop Overview

This workshop is part of the **18th GeoMundus Conference**, which focuses on the use of geospatial intelligence to strengthen disaster resilience, improve risk understanding and support emergency management.

The workshop presents a practical and reproducible workflow for transforming open Earth Observation and geospatial datasets into information that can support **wildfire risk assessment and operational decision support**.

The training uses the **SIDENCA (Sistema Inteligente para la Detección de Riesgos y Toma de Decisiones ante Catástrofes)** project as a practical context. Participants will explore how satellite imagery, environmental variables, demographic information, built-environment data, meteorological observations and sensor data can be integrated into a common spatial modelling framework.

The workshop follows a recent wildfire case study from the **Comunitat Valenciana, Spain** and provides participants with an overview of the workflow from fire-event mapping and data preparation to machine-learning-based wildfire risk modelling, fire-spread simulation and operational decision support.
---

## About the SIDENCA Project

**SIDENCA** (*Sistema Inteligente para la Detección de Riesgos y Toma de Decisiones ante Catástrofes*) is a strategic R&D project focused on developing an intelligent, interoperable and scalable decision-support platform for managing climate-related disasters in the **Comunitat Valenciana, Spain**.

The project integrates **Earth Observation, geospatial data, artificial intelligence, Bayesian spatio-temporal modelling, sensor networks, semantic interoperability and edge-cloud computing** to support disaster risk management. SIDENCA addresses multiple climate-related hazards, including **wildfires, floods, severe storms, heat waves and droughts**, with the aim of providing timely and actionable information throughout the disaster management cycle.

## SIDENCA Decision-Support Platform

The main outcome of SIDENCA is a **web-based geoportal** that integrates heterogeneous geospatial and sensor data to provide actionable information for emergency management. The platform supports interactive GIS visualisation, hazard and risk information, sensor monitoring, forecasting, damage assessment and decision-support workflows.

In this workshop, selected components of the SIDENCA project will be used as the basis for practical training. Participants will work through the different stages of a reproducible workflow, from accessing and preparing open geospatial datasets to developing wildfire risk and fire spread information products.

---

## Project Funding

SIDENCA is funded by the **Generalitat Valenciana (IVACE+i)** and the **European Union through the European Regional Development Fund (ERDF)**.

---

## More Information

- [GEOTEC – Universitat Jaume I](https://geotec.uji.es/projects/sidenca/)
- [Universitat de València – SIDENCA](https://www.uv.es/uvweb/university-research-institute-robotics-information-communication-technologies/en/departments-news/sidenca-will-strengthen-prevention-disasters-caused-climate-change-valencian-community-1285923268336/Novetat.html?id=1286466146940)
- [REDIT – SIDENCA Project](https://redit.habitat-sostenible.es/proyectos/proyecto-sidenca-sistema-inteligente-para-la-deteccion-de-riesgos-y-toma-de-decisiones-ante-catastrofes/)
- [AINIA – SIDENCA](https://www.ainia.com/en/proyectos-publicos/sidenca/)
- [Albavalor](https://albavalor.es/)

---

## Workshop Training

## Software and Tools

The workshop will use a combination of open-source and freely available geospatial tools and data platforms.

| Tool / Platform | Purpose |
|-----------------|---------|
| Python | Geospatial analysis and machine learning |
| Google Colab | Cloud-based coding environment |
| QGIS | Desktop GIS analysis |


> Specific packages, scripts and environments used during the training will be provided through this repository where applicable.
---
## Data to Be Shared

The workshop datasets will be shared through **Google Drive**. The shared data will be organised according to the different stages of the workshop workflow. Participants can access the relevant datasets as they progress through the training.

### Workshop Data Repository

| Dataset / Data Group | Description | Link |
|----------------------|-------------|------|
| Sentinel-2 imagery | Pre- and post-fire satellite imagery | Google Drive |
| Fire-event data | Fire perimeter and event information | Google Drive |
| Modelling dataset | Harmonised workshop modelling dataset | Google Drive |
| Machine-learning outputs | Example model outputs and predictions | Google Drive |
| Workshop outputs | Reference results and supporting files | Google Drive |

> **Note:** The Google Drive links will be added before the workshop. Participants are encouraged to access the relevant datasets before the corresponding workshop sessions.

### Data Access Notes

| Item | Details |
|------|---------|
| Platform | Google Drive |
| Organisation | By workshop stage |
| Access | Links provided before workshop |
| Recommendation | Download relevant data before each session |
---

## Block 1 — Wildfire Case Study

**Purpose:** Introduce the common case study and the central modelling question that guides the entire workshop.

**What to include:**

| Item | Description |
|------|-------------|
| Event Details | Start date (25 July 2026), location (near La Vall d'Uixó), affected area (Serra d'Espadà massif) |
| Modelling Question | Can freely available data estimate spatial probability of wildfire occurrence? |
| Analysis Unit | Frozen 100 m × 100 m grid |
| Objective | Demonstrate a reproducible workflow, not just produce a risk map |

---

### Block 2 — Satellite Imagery and Fire-Event Mapping

**Purpose:** Use Earth Observation data to identify and characterise the wildfire event.

**What to include:**

| Item | Description |
|------|-------------|
| Data Sources | Sentinel-2 Level-2A, Copernicus Data Space, Google Earth Engine, MODIS/VIIRS, Copernicus EMS Rapid Mapping, EMSR905 |
| Satellite Analysis | Natural-colour composites, false-colour composites, NBR, dNBR, burn-severity information |
| NBR Formula | NBR = (B8A − B12) / (B8A + B12) |
| dNBR Formula | dNBR = NBR(pre-fire) − NBR(post-fire) |
| Important Note | dNBR is a post-fire assessment product and must NOT be used as a predictor in the occurrence model (information leakage) |

**Expected Outputs:**

| Output | Description |
|--------|-------------|
| Pre-fire satellite composite | Before the fire event |
| Post-fire satellite composite | After the fire event |
| NBR layers | Burn ratio indices |
| dNBR layer | Difference NBR |
| Burn-severity map | Classified burn severity |
| Fire-event reference information | Event metadata and perimeter |

---

### Block 3 — Earth Observation and Covariates

**Purpose:** Assemble environmental, demographic and built-environment variables that may explain spatial variation in wildfire occurrence.

**What to include:**

| Sub-Block | Variables | Data Sources |
|-----------|-----------|--------------|
| Topography | Elevation, slope, aspect (sine/cosine), TPI, terrain ruggedness, solar radiation | Copernicus DEM GLO-30, PNOA MDT05 |
| Land Cover and Fuel | Land-cover class fractions, modal class, tree-cover density, fuel information | ESA WorldCover 2021, CORINE, Mapa Forestal, Copernicus HRL |
| Vegetation | NDVI, EVI, NDMI (as anomalies where suitable) | Sentinel-2, MODIS, Google Earth Engine |
| Built Environment | Building count, footprint area, fraction, mean size, distance to nearest building, counts in 250 m / 500 m windows | Open Buildings, OpenStreetMap, Catastro |
| Population and Settlement | Population count, density, built-up indicators, degree of urbanisation | WorldPop, GHSL, INE |
| Human Activity and Infrastructure | Night-time light intensity, distance to roads, tracks, settlements, power lines | VIIRS DNB, OpenStreetMap |
| Fire History | Number of previous fires, years since last fire, previously burned areas | EFFIS, Generalitat Valenciana |

**Expected Output:** An integrated collection of covariates aligned to the common 100 m reference grid.

---


### Block 4 — Meteorological and Sensor Data

**Purpose:** Incorporate meteorological conditions and sensor observations that influence wildfire occurrence and behaviour.

**What to include:**

| Sub-Block | Variables / Steps | Notes |
|-----------|-------------------|-------|
| Meteorological Variables | Max/min/mean temperature, min relative humidity, precipitation, mean/max wind speed, wind direction, insolation | AEMET stations; wider area to reduce edge effects |
| Meteorological Interpolation | Station observations → Regression model → Residual analysis → Residual interpolation → Reconstruction → 100 m surface | Kriging uncertainty retained as additional layer |
| Wind Variables | Wind direction → u and v components → Spatial interpolation → Reconstruction | Avoids incorrect arithmetic averaging of circular data |
| Fire-Weather Indicators | FFMC, DMC, DC, ISI, BUI, FWI, VPD, consecutive dry days, precipitation deficits, SPEI | Short- and long-term environmental conditions |
| SIDENCA Sensor Data | IoT, air-quality, soil-moisture, UAV, field observations | Point observations → Quality control → Spatial interpolation → 100 m raster |

**Expected Output:** Daily meteorological and sensor-derived surfaces aligned to the common 100 m reference grid.

---

### Block 5 — Data Harmonisation and Modelling Dataset

**Purpose:** Harmonise all datasets to the frozen 100 m reference grid and prepare an analysis-ready modelling dataset.

**What to include:**

| Sub-Block | Details |
|-----------|---------|
| Resampling Methods | Continuous fine-resolution: mean (with SD where relevant); Continuous coarse-resolution: bilinear or physiographic downscaling; Categorical: class fractions and modal class; Counts: aggregation conserving totals; Circular: decomposition before processing |
| Quality Control | Geometry consistency, grid alignment, physical value ranges, missing values, spatial patterns of missingness, highly correlated variables, multicollinearity (VIF screening) |
| Fire-Occurrence Response | Binary variable: 1 = burned, 0 = non-burned; stratified case-control sampling; negative samples avoid sea, bare rock, urban cores |
| Sampling Stratification | Land cover, elevation, municipality |

**Expected Output:** An analysis-ready modelling dataset containing permanent grid-cell ID, wildfire occurrence response, environmental covariates, population variables, built-environment variables, meteorological variables, sensor-derived variables and fire-history variables.

---

### Block 6 — Machine-Learning Wildfire Risk Model

**Purpose:** Use the integrated modelling dataset to estimate the spatial probability of wildfire occurrence.

**What to include:**

| Sub-Block | Details |
|-----------|---------|
| Model Approaches | Random Forest (variance benchmark), LightGBM (primary), XGBoost (alternative) |
| Feature Engineering | Fuel continuity, burnable fraction, contiguous burnable-patch size, moving-window means (300 m, 500 m, 1 km), aspect–wind relationships, wind × slope, FWI × fuel-continuity |
| Model Validation | Spatial block cross-validation, leave-one-fire-out validation, temporal hold-out validation; example: train 2006–2022, validate 2023–2025, test 2026 |
| Model Evaluation | PR-AUC, ROC-AUC, Brier score, log loss, reliability diagrams, spatial residual analysis, Moran's I |
| Model Interpretation | SHAP analysis, local SHAP explanations, Accumulated Local Effects (ALE), spatial examination of predictions |

**Expected Output:** A calibrated wildfire probability map representing the estimated spatial probability of wildfire occurrence.

---
### Block 7 — Operational Decision Support

**Purpose:** Connect modelling outputs to an operational decision-support workflow.

**What to include:**

| Sub-Block | Details |
|-----------|---------|
| Operational Workflow | New daily data → Data ingestion → Quality control → Data harmonisation → Risk prediction → Fire-spread simulation → Exposure & impact assessment → Operational dashboard |
| Decision-Support Information | Current wildfire risk, high-risk areas, population exposure, building exposure, critical infrastructure, protected areas, fire-spread scenarios, model uncertainty, change in risk over time |
| Key Principle | Risk + Exposure = Operational Priority |
| Operational Dashboard | Integrated view of risk, exposure, fire spread, uncertainty, changes over time |
| Uncertainty Communication | Uncertainty should be communicated alongside predicted risk; graceful degradation when data sources are unavailable |
| Operational Outputs | Wildfire preparedness, emergency response, resource prioritisation, exposure assessment, situational awareness, post-fire assessment |

**Expected Output:** An operational risk and exposure concept that can support wildfire preparedness, response and recovery.

---







*Detailed workshop workflow and training materials will be added here.*