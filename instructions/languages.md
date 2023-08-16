## Reconciling languages to Wikidata

1. Load `DATE-languages-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-languages-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][language_workflow] (On the left, go to `Undo/Redo`, `Apply`, paste the JSON code, and `Perform operations`)
3. Copy and clean `language_as_recorded` column and reconcile new `recon-language` column against language type (Q34770): [JSON][language_recon]
4. Apply list of previously reconciled or known languages: [JSON][language_known]
5. Manually reconcile and update known languages: *edit [JSON][language_known] and submit pull request*
6. Add `authorized_label_add` and `structured_value_add` columns for newly reconciled values; finalize workflow: [JSON][language_finalize]
7. Remove any facets and filters
8. Export full CSV from OpenRefine (retain file name)

[language_workflow]:  json/language/010-language-workflow.json
[language_recon]:     json/language/030-language-recon.json
[language_known]:     json/language/040-language-known.json
[language_finalize]:  json/language/090-language-finalize.json

```
json/language/010-language-workflow.json
json/language/030-language-recon.json
json/language/040-language-known.json
json/language/090-language-finalize.json
```
