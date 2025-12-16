## Reconciling places to TGN

1. Load `DATE-places-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-places-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][place_workflow]
3. Copy `place_as_recorded` column and reconcile new `recon-place` column against TGN vocabulary: [JSON][place_recon]
4. Add `authorized_label_add` and `structured_value_add` columns for newly reconciled values: [JSON][place_values]
5. Open OpenRefine in another tab/window; load `places-ds-authority.csv` ([FILE][place_authority]) into this new OpenRefine tab; delete any previously loaded versions of the authority file in OpenRefine (Menu option: `Open project` and browse project list, select X and confirm)
6. Add `ds_qid_add` column; finalize workflow: [JSON][place_finalize]
7. Remove any facets and filters
8. Export full CSV from OpenRefine (retain file name)

[place_workflow]:    json/place/010-place-workflow.json
[place_recon]:       json/place/030-place-recon.json
[place_values]:      json/place/040-place-values.json
[place_finalize]:    json/place/090-place-finalize.json
[place_authority]:   authorities/places-ds-authority.csv

```
json/place/010-place-workflow.json
json/place/030-place-recon.json
json/place/040-place-values.json
json/place/090-place-finalize.json
authorities/places-ds-authority.csv
```
