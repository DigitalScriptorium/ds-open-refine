## OpenRefine Instructions for Merging New Reconciled Data with Existing Reconciliations in Data Dictionaries

### Isolating new values from enriched data CSVs
1. Load enriched data CSV into OpenRefine, rename `VALUE-add` where `VALUE` is the type of metadata (genres, languages, names, subjects, etc.)
2. On the `structured_value` column, facet by selecting `Facet -> Customized facets -> Facet by blank`
3. Select `TRUE` for applied facet to `structured_value` column
4. On the `structured_value_add` column, facet by selecting `Facet -> Customized facets -> Facet by blank`
5. Select `FALSE` for applied facet to `structured_value_add` column
6. `Export -> Comma separated value` file from OpenRefine

### Integrating new values from enriched data with data dictionaries

1. Copy `VALUE.csv` from ds-data reconciled repository to local machine for the type of metadata to be merged
2. Load `VALUE.csv` and `VALUE-add.csv` simultaneously into OpenRefine
3. Name file `VALUE-new`

#### Sorting data values alphabetically by as_recorded strings
4. On `VALUE_as_recorded` column, apply `Sort...` with the following parameters: text, case sensitive, a-z
5. From row view selector, find `Sort` and choose `Reorder rows permanently`

#### Checking for duplicate rows
6. On `VALUE_as_recorded` column, `Edit column -> Join columns...`
7. Within the join columns menu, choose all columns that apply which may render the row unique, select `Write result in new column named` and type into the text box `duplicate_check`
8. On the newly created `duplicate_check` column, facet by selecting `Facet -> Customized facets -> Duplicates facet`
9. Select `TRUE` for applied facet on `duplicate_check` column to find any duplicate rows
10. Star one of each duplicate row, and on the `All` column, facet by selecting `Facet -> Facet by star`
11. Select `TRUE` for applied facet on starred rows
12. On `All` column, select `Edit rows -> Remove matching rows`

#### Removing working columns and merging new reconciliations with previous ones in data dictionaries
13. Apply JSON recipe to remove unnecessary columns, merge new data values into existing data, remove whitespace: [JSON][merge-clean-recon-data]
14.  `Export -> Comma separated value` file from OpenRefine
15.  Add exported `VALUE-new.csv` to ds-data/reconciled/terms repository
16.  Deprecate/archive old version to `Batch` directory
17.  Rename `VALUE-new.csv` to `VALUE.csv` 


[merge-clean-recon-data]: json/all/010-merge-clean-recon-data.json

```
json/all/010-merge-clean-recon-data.json
```
