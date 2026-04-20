# data/

Place `combined_metropolitan_data_bexley_street_only.csv` in this folder before running the notebooks.

## Source

Metropolitan Police open crime data filtered to the London Borough of Bexley.

Download the original monthly files from [data.police.uk](https://data.police.uk/data/) covering **March 2023 – February 2026**, then run the merging and filtering steps described in `notebooks/01_hotspot_prediction.ipynb` (Deliverable 1) to reproduce this file.

## Note on file size

The CSV is too large to track directly in git. If you want to host it, consider:
- Adding it to a GitHub Release as an asset
- Hosting it on Google Drive and updating the notebook load path
- Using Git LFS (`git lfs track "data/*.csv"`)
