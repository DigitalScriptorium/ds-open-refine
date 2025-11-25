## Reconciling materials to AAT

1. Load `DATE-materials-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-materials-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][material_workflow]
3. Copy `material_as_recorded` column, match new `recon-material` column against fixed list from AAT, add `authorized_label_add` and `structured_value_add` columns: [JSON][material_values]
4. Open OpenRefine in another tab/window; load `materials-ds-authority.csv` ([FILE][material_authority]) into this new OpenRefine tab
5. Add `ds_qid_add` column for reconciled values and finalize reconciliation workflow: [JSON][material_finalize]
6. Remove any facets and filters
7. Export full CSV from OpenRefine (retain file name)

[material_workflow]:    json/material/010-material-workflow.json
[material_values]:      json/material/030-material-values.json
[material_finalize]:    json/material/090-material-finalize.json
[material_authority]:   authorities/materials-ds-authority.csv

```
json/material/010-material-workflow.json
json/material/030-material-values.json
json/material/090-material-finalize.json
authorities/materials-ds-authority.csv
```
