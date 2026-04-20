# Bexley Crime Hotspot Analysis

A data mining and spatial network analysis project investigating crime patterns in the **London Borough of Bexley** using Metropolitan Police open data.

---

## Project Overview

This project has two parts:

### Part 1 — Hotspot Prediction (`notebooks/01_hotspot_prediction.ipynb`)
Uses machine learning to predict which Bexley LSOAs (Lower Super Output Areas) are likely to become crime hotspots in a given month.

- Cleans and explores 3 years of Metropolitan Police street-level data (March 2023 – February 2026)
- Engineers a binary hotspot target using the upper quartile of monthly crime counts
- Trains and compares Logistic Regression, Decision Tree, and Random Forest classifiers
- Tunes the best model using GridSearchCV
- Produces interactive heatmaps and LSOA-level crime visualisations
- Outputs a **safety score (0–100)** for each LSOA via an interactive UI

### Part 2 — Crime Diffusion Analysis (`notebooks/02_crime_diffusion_igraph.ipynb`)
Extends the project by modelling Bexley's LSOAs as a **spatial network** using `igraph`, asking:

> When an LSOA becomes a crime hotspot, do its geographic neighbours become hotspots in the following months?

- Builds a spatial graph where nodes are LSOAs and edges connect areas within 1.2 km
- Measures diffusion rates and lift multipliers at lag 1 and lag 2 months
- Identifies **diffusion hub** LSOAs — areas most likely to seed crime in their neighbours
- Visualises the network and hub rankings on interactive folium maps

---

## Repository Structure

```
bexley-crime-analysis/
│
├── notebooks/
│   ├── 01_hotspot_prediction.ipynb       # Main ML project
│   └── 02_crime_diffusion_igraph.ipynb   # igraph diffusion extension
│
├── data/
│   └── combined_metropolitan_data_bexley_street_only.csv
│
├── outputs/
│   └── (generated maps, charts, and model files saved here)
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Data Source

Metropolitan Police open crime data — monthly street-level CSV files covering March 2023 to February 2026, filtered to the London Borough of Bexley.

Source: [data.police.uk](https://data.police.uk/data/)

---

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/bexley-crime-analysis.git
cd bexley-crime-analysis
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the notebooks
Open either notebook in Jupyter or Google Colab. Both notebooks load the dataset from the `data/` folder automatically.

> **Google Colab users:** The notebooks will prompt you to upload the CSV if it is not found locally. Alternatively, update the file path to point to your Google Drive.

---

## Requirements

See `requirements.txt` for the full list. Key libraries:

| Library | Purpose |
|---|---|
| `pandas` / `numpy` | Data handling |
| `scikit-learn` | Machine learning models |
| `igraph` | Spatial network analysis |
| `folium` | Interactive maps |
| `matplotlib` / `seaborn` | Charts and visualisation |

---

## Key Results

| Finding | Detail |
|---|---|
| Best model | Random Forest (tuned) |
| Hotspot threshold | 75th percentile of monthly LSOA crime count |
| Diffusion detected | Neighbours of hotspot LSOAs become hotspots at a higher rate than baseline |
| Top diffusion hubs | See `02_crime_diffusion_igraph.ipynb` Section 8 |

---

## Acknowledgements

Crime data provided by the Metropolitan Police Service via [data.police.uk](https://data.police.uk) under the [Open Government Licence](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).
