# Working folder (`DATA_DIR`)

This folder holds all input files and, after running the notebooks, all outputs. Its content is **not** part of the repository (see `.gitignore`).

## Inputs to place here

| Path | Content | Where to get it |
|---|---|---|
| `Sample_Data.xlsx` | Non-target screening results, one column per sample | Your own data, or the synthetic test data in `../example_data/` |
| `geo_metadata_outputs/household_metadata_priors.csv` | Optional household priors (see `docs/household_priors.md`) | Your own data, or the synthetic test data `../example_data/geo_metadata_outputs/household_metadata_priors.csv`; not needed if `USE_GEO_PRIORS = False` in Part 2 |
| `lookups/source_class_mapping.xlsx` | Mapping of source categories to the reporting classes `source_class` / `source_class_domain` | Your own data, or the synthetic test data `../example_data/lookups/source_class_mapping.xlsx` |
| `Own_Household_Products.csv`, `Own_Household_Products_Metadata.csv` | Own analyzed household products | Your own data, or the synthetic test data `../example_data/Own_Household_Products.csv`, `../example_data/Own_Household_Products_Metadata.csv` |
| `Literature_Products.csv` | Consumer-product compounds compiled from the literature | Your own data, or the synthetic test data `../example_data/Literature_Products.csv` |
| `CPDat/product_compositions.tsv`, `CPDat/products.tsv`, `CPDat/product_use_categories.tsv` | US EPA CPDat v4.0 (processed) | Rebuild from the original (https://www.epa.gov/chemical-research/chemical-and-products-database-cpdat) with https://github.com/r3bryk/cpdat_v4.0_cleanup, or the synthetic test data in `../example_data/CPDat` |
| `FooDB.csv` | FooDB v1.0 (processed; tab-separated) | Rebuild from the original (https://foodb.ca) with https://github.com/r3bryk/foodb_v1.0_cleanup, or the synthetic test data `../example_data/FooDB.csv` |
| `SPECIATE.xlsx` | US EPA SPECIATE v5.4 (processed) | Rebuild from the original (https://www.epa.gov/air-emissions-modeling/speciate) with https://github.com/r3bryk/speciate_v5.4_cleanup, or the synthetic test data `../example_data/SPECIATE.xlsx` |
| `SPECIEUROPE.xlsx` | JRC SPECIEUROPE v3.0 (processed) | Rebuild from the original (https://source-apportionment.jrc.ec.europa.eu/Specieurope/index.aspx) with https://github.com/r3bryk/specieurope_v3.0_cleanup, or the synthetic test data `../example_data/SPECIEUROPE.xlsx` |

**Testing without the real databases:** `../example_data/` contains small synthetic versions of **all** inputs in this table (same file names and subfolders; 60 sources per database). Copy its content into this folder to test the pipeline; see [example_data/README.md](../example_data/README.md).

**License of the shared data:** CC BY-NC 4.0 (non-commercial; required because the source database contains FooDB-derived data). Please also cite the original databases (see the main README).

Formats and mandatory columns: [docs/input_data.md](../docs/input_data.md).

## Outputs created here

`databases_id_w_suffix/`, `databases_standardized/`, `all_sources_aggregated/`, `masked_sources/`, `lookups/`, `alpha_tuning/`, `validation_outputs/`, `set_cover_outputs/` (and `geo_metadata_outputs/geo_mapping_check.csv`); see [docs/codebook.md](../docs/codebook.md). A full run needs about 6 GB of free disk space.
