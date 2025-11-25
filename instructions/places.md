## Reconciling places to TGN

1. Load `DATE-places-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-places-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][place_workflow]
3. Copy `place_as_recorded` column and reconcile new `recon-place` column against TGN vocabulary: [JSON][place_recon]
4. Apply list of previously reconciled or known places: [JSON][place_known]
5. Manually reconcile and update known places: *edit [JSON][place_known] and submit pull request*
6. Add `authorized_label_add` and `structured_value_add` columns; finalize workflow: [JSON][place_finalize]
7. Remove any facets and filters
8. Export full CSV from OpenRefine (retain file name)

[place_workflow]:    json/place/010-place-workflow.json
[place_recon]:       json/place/030-place-recon.json
[place_known]:       json/place/040-place-known.json
[place_finalize]:    json/place/090-place-finalize.json

```
json/place/010-place-workflow.json
json/place/030-place-recon.json
json/place/040-place-known.json
json/place/090-place-finalize.json
```
