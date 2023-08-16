## Reconciling materials to AAT

1. Load `DATE-materials-DATATYPE-INSTITUTION.csv` into OpenRefine; rename `DATE-materials-DATATYPE-INSTITUTION-enriched.csv`
2. Add workflow columns: [JSON][material_workflow]
3. Copy `material_as_recorded` column, match new `recon-material` column against fixed list from AAT, add `authorized_label_add` and `structured_value_add` columns; finalize workflow: [JSON][material_finalize]
4. Remove any facets and filters
5. Export full CSV from OpenRefine (retain file name)

[material_workflow]:  json/material/010-material-workflow.json
[material_finalize]:  json/material/090-material-finalize.json

```
json/material/010-material-workflow.json
json/material/090-material-finalize.json
```
