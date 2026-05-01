# Predicting & Analysing Crime in Bexley Borough

**Metropolitan Police Data | Machine Learning | Spatial Network Analysis**

---

## Project Overview

This project analyses street-level crime data from the Metropolitan Police Service across Bexley Borough (2023–2026). It has two parts:

| Notebook | What it does |
|---|---|
| `01_hotspot_prediction.ipynb` | Builds a Random Forest model to predict which LSOAs will become crime hotspots |
| `02_crime_diffusion_igraph_final.ipynb` | Extends the model with spatial network analysis to measure whether hotspots spread to neighbouring areas |

---

## Viewing the Results

The easiest way to see all visualisations is to open the self-contained report:

> **📄 [`crime_diffusion_report.html`](crime_diffusion_report.html)**  
> Download this file and open it in any web browser. No internet connection or software installation required.

The report includes:
- An interactive spatial network map of all 149 Bexley LSOAs
- An interactive diffusion hub map showing which areas seed crime in their neighbours
- Statistical charts (crime trends, diffusion
