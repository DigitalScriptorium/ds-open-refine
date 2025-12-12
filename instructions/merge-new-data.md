## OpenRefine Instructions for Merging New Reconciled Data with Existing Reconciliations in Data Dictionaries

### Isolating new values from enriched data CSVs
1. Load enriched data CSV into OpenRefine, rename `VALUE-add-DATE` where `VALUE` is the type of metadata (genres, languages, names, subjects, etc.) and DATE is the current date in YYYYMMDD format
2. On the `ds_qid_add` column, facet by selecting `Facet -> Customized facets -> Facet by blank`
3. Select `FALSE` for applied facet to `ds_qid_add` column
4. `Export -> Comma-separated value` file from OpenRefine to local machine

### Integrating new values from enriched data with existing data dictionaries

1. Copy `VALUE.csv` from [`ds-data/terms/reconciled`](https://github.com/DigitalScriptorium/ds-data/tree/main/terms/reconciled) repository to local machine for the type of metadata to be merged
2. Load `VALUE.csv` and `VALUE-add-DATE.csv` simultaneously into OpenRefine
3. Name file `VALUE-new-DATE`

#### Checking for duplicate rows
4. On `VALUE_as_recorded` column, `Edit column -> Join columns...`
5. Within the join columns menu, choose all columns that apply which may render the row unique, select `Write result in new column named` and type into the text box `duplicate_check`
6. On the newly created `duplicate_check` column, facet by selecting `Facet -> Customized facets -> Duplicates facet`
7. Select `TRUE` for applied facet on `duplicate_check` column to find any duplicate rows
8. Star one of each duplicate row to be removed, and on the `All` column, facet by selecting `Facet -> Facet by star`
9. Select `TRUE` for applied facet on starred rows
10. On `All` column, select `Edit rows -> Remove matching rows`

#### Removing working columns and merging new reconciliations with previous ones in data dictionaries
11. On the `ds_qid_add` column, facet by selecting `Facet -> Customized facets -> Facet by blank`
12. Select `FALSE` for applied facet to `ds_qid_add` column
13. Apply JSON recipe to merge new data values into existing data, remove unnecessary columns, remove whitespace
  - for name data: [JSON][merge-clean-name-recon-data]
  - for title data: [JSON][merge-clean-title-recon-data]
  - for all other data: [JSON][merge-clean-other-recon-data]


#### Sorting data values alphabetically by as_recorded strings
14. On `VALUE_as_recorded` column, apply `Sort...` with the following parameters: text, case sensitive, a-z
15. From row view selector, find `Sort` and choose `Reorder rows permanently`
16. `Export -> Comma-separated value` file from OpenRefine to local machine

### Updating data dictionaries in ds-data repository
17.  Add exported `VALUE-new-DATE.csv` to [`ds-data/terms/reconciled`](https://github.com/DigitalScriptorium/ds-data/tree/main/terms/reconciled) repository from local machine
18.  Deprecate/archive old version of `VALUE.csv` by moving to [`ds-data/terms/reconciled/deprecated`](https://github.com/DigitalScriptorium/ds-data/tree/main/terms/reconciled/deprecated) under the appropriately dated directory (i.e., create a new directory with the current date under the current year)
19.  Return to `reconciled` directory and rename `VALUE-new-DATE.csv` to `VALUE.csv`


[merge-clean-name-recon-data]:  json/all/010-merge-clean-name-recon-data.json
[merge-clean-title-recon-data]: json/all/020-merge-clean-title-recon-data.json
[merge-clean-other-recon-data]: json/all/030-merge-clean-other-recon-data.json

```
json/all/010-merge-clean-name-recon-data.json
json/all/020-merge-clean-title-recon-data.json
json/all/030-merge-clean-other-recon-data.json
```
