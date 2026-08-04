# Data files

The FITS catalogues in `raw/` and `processed/` are generated or downloaded by
the notebooks and are intentionally excluded from Git. This keeps the
repository small and avoids redistributing third-party catalogue data.

## Recreating the data

Run the notebooks in numerical order from the project root:

1. `Notebooks/01_pleiades_data_query.ipynb` downloads and combines the Gaia DR3
   query into `raw/`.
2. `Notebooks/02_data_cleaning.ipynb` creates the cleaned field catalogue in
   `processed/`.
3. `Notebooks/03_dbscan_membership.ipynb` writes the provisional candidate
   catalogue.
4. `Notebooks/04_colour_magnitude_diagram.ipynb` adds CMD and photometric
   quality fields.
5. `Notebooks/05_catalogue_comparison.ipynb` downloads the published reference
   catalogue when needed and writes the final comparison products.

The `.gitkeep` files preserve the empty directory structure in a fresh clone.

## Main generated products

- `processed/gaia_dr3_pleiades_candidates_catalogue_compared.fits` is the final
  1,185-source candidate catalogue.
- `processed/hunt_reffert_2023_members_missed_inside_3deg.fits` is the audit of
  176 published members omitted inside the query footprint.

If these products are distributed separately through a GitHub release or data
archive, include the Gaia and Hunt & Reffert catalogue citations from the main
README.
