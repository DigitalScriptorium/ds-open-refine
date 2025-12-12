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
4. Apply JSON recipe to conduct a duplicate check based on the `VALUE_as_recorded` column and all other columns that may render the row unique
- for genre data: [JSON][duplicate_check_genre]
- for language data: [JSON][duplicate_check_language]
- for name data: [JSON][duplicate_check_name]
- for named-subject and subject data: [JSON][duplicate_check_subject]
- for title data: [JSON][duplicate_check_title]
- for all other data: [JSON][duplicate_check_other]
5. On the newly created `duplicate_check` column, facet by selecting `Facet -> Customized facets -> Duplicates facet`
6. Select `TRUE` for applied facet on `duplicate_check` column to find any duplicate rows
7. Star one of each duplicate row to be removed, and on the `All` column, facet by selecting `Facet -> Facet by star`
8. Select `TRUE` for applied facet on starred rows
9. On `All` column, select `Edit rows -> Remove matching rows`

#### Removing working columns and merging new reconciliations with previous ones in data dictionaries
10. On the `ds_qid_add` column, facet by selecting `Facet -> Customized facets -> Facet by blank`
11. Select `FALSE` for applied facet to `ds_qid_add` column
12. Apply JSON recipe to merge new data values into existing data, remove unnecessary columns, remove whitespace
  - for name data: [JSON][merge-clean-name-recon-data]
  - for title data: [JSON][merge-clean-title-recon-data]
  - for all other data: [JSON][merge-clean-other-recon-data]

#### Sorting data values alphabetically by as_recorded strings
13. On `VALUE_as_recorded` column, apply `Sort...` with the following parameters: text, case sensitive, a-z
14. From row view selector, find `Sort` and choose `Reorder rows permanently`
15. `Export -> Comma-separated value` file from OpenRefine to local machine

### Updating data dictionaries in ds-data repository
16.  Add exported `VALUE-new-DATE.csv` to [`ds-data/terms/reconciled`](https://github.com/DigitalScriptorium/ds-data/tree/main/terms/reconciled) repository from local machine
17.  Deprecate/archive old version of `VALUE.csv` by moving to [`ds-data/terms/reconciled/deprecated`](https://github.com/DigitalScriptorium/ds-data/tree/main/terms/reconciled/deprecated) under the appropriately dated directory (i.e., create a new directory with the current date under the current year)
18.  Return to `reconciled` directory and rename `VALUE-new-DATE.csv` to `VALUE.csv`


[duplicate_check_genre]:        json/all/check/010-duplicate-check-genre.json
[duplicate_check_language]:     json/all/check/020-duplicate-check-language.json
[duplicate_check_name]:         json/all/check/030-duplicate-check-name.json
[duplicate_check_subject]:      json/all/check/040-duplicate-check-subject.json
[duplicate_check_title]:        json/all/check/050-duplicate-check-title.json
[duplicate_check_other]:        json/all/check/060-duplicate-check-other.json
[merge-clean-name-recon-data]:  json/all/merge/010-merge-clean-name-recon-data.json
[merge-clean-title-recon-data]: json/all/merge/020-merge-clean-title-recon-data.json
[merge-clean-other-recon-data]: json/all/merge/030-merge-clean-other-recon-data.json

```
json/all/check/010-duplicate-check-genre.json
json/all/check/020-duplicate-check-language.json
json/all/check/030-duplicate-check-name.json
json/all/check/040-duplicate-check-subject.json
json/all/check/050-duplicate-check-title.json
json/all/check/060-duplicate-check-other.json
json/all/merge/010-merge-clean-name-recon-data.json
json/all/merge/020-merge-clean-title-recon-data.json
json/all/merge/030-merge-clean-other-recon-data.json
```
