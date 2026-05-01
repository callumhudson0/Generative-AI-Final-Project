# Predicting & Analysing Crime in Bexley Borough

**Metropolitan Police Data | Machine Learning | Spatial Network Analysis**

---

## Project Overview

This project analyses street-level crime data from the Metropolitan Police Service across Bexley Borough (2023–2026). It has two parts:

| Notebook | What it does |
|---|---|
| `01_main_analysis.ipynb` | Builds a Random Forest model to predict which LSOAs will become crime hotspots |
| `02_crime_diffusion_igraph_final.ipynb` | Extends the model with spatial network analysis to measure whether hotspots spread to neighbouring areas |

---

## Viewing the Results

The easiest way to see all visualisations is to open the self-contained report:

> **📄 [`crime_diffusion_report.html`](crime_diffusion_report.html)**  
> Download this file and open it in any web browser. No internet connection or software installation required.

The report includes:
- An interactive spatial network map of all 149 Bexley LSOAs
- An interactive diffusion hub map showing which areas seed crime in their neighbours
- Statistical charts (crime trends, diffusion lift, top crime types)
- Written explanation of findings and methodology

---

## Repository Structure

```
├── README.md                                        ← You are here
├── crime_diffusion_report.html                      ← Open this to view all results
├── 01_main_analysis.ipynb                           ← Main hotspot prediction notebook
├── 02_crime_diffusion_igraph_final.ipynb            ← Crime diffusion extension notebook
└── combined_metropolitan_data_bexley_street_only.csv  ← Source dataset
```

---

## Key Findings

- **59,748 incidents** recorded across **149 LSOAs** in Bexley
- A hotspot LSOA's neighbours have a **30.2% chance** of becoming hotspots the following month, versus a **25.8% baseline** — a **1.17× lift**
- This confirms **crime diffusion** (near-repeat victimisation) is present in Bexley
- Top diffusion hubs: **Bexley 015A**, **Bexley 004B**, **Bexley 004A**
- Proactive policing in hub LSOAs could suppress cascading hotspot formation across multiple areas

---

## Data Source

Metropolitan Police Service — street-level crime data, publicly available via [data.police.uk](https://data.police.uk).

---

## Tools & Libraries

`Python` · `pandas` · `scikit-learn` · `igraph` · `folium` · `seaborn` · `matplotlib`
