## Reconciling languages to Wikidata

1. Load `DATE-languages-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-languages-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][language_workflow]
3. Copy and clean `language_as_recorded` column and reconcile new `recon-language` column against language type (Q34770): [JSON][language_recon]
4. Add `authorized_label_add` and `structured_value_add` columns for newly reconciled values: [JSON][language_values]
5. Open OpenRefine in another tab/window; load `languages-ds-authority.csv`([FILE][language_authority]) into this new OpenRefine tab
6. Add `ds_qid_add` column for reconciled values and finalize reconciliation workflow: [JSON][language_finalize]
7. Remove any facets and filters
8. Export full CSV from OpenRefine (retain file name)

[language_workflow]:  json/language/010-language-workflow.json
[language_recon]:     json/language/030-language-recon.json
[language_values]:    json/language/040-language-values.json
[language_finalize]:  json/language/090-language-finalize.json
[language_authority]: authorities/languages-ds-authority.csv

```
json/language/010-language-workflow.json
json/language/030-language-recon.json
json/language/040-language-values.json
json/language/090-language-finalize.json
```
