## Reconciling names to Wikidata

1. Load `DATE-names-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-names-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][name_workflow] (On the left, go to `Undo/Redo`, `Apply` and paste the JSON code, and `Perform operations`)
3. Copy `name_as_recorded` column and reconcile new `recon-human` column against human type (Q5): [JSON][name_recon_human]
4. Apply list of previously reconciled or known human names: 0. [JSON][name_known_human_0], 1. [JSON][name_known_human_1], 2. [JSON][name_known_human_2]
5. Manually reconcile and update known human names: *edit [JSON][name_known_human_2] and submit pull request*
6. Add `human-label`, `instance-of-human`, and `human-qid` columns; rename reconciliation column to `recon-organization` to reconcile against organization type (Q43229): [JSON][name_recon_org]
7. Apply list of previously reconciled or known organization names: [JSON][name_known_org]
8. Manually reconcile and update known organization names: *edit [JSON][name_known_org]*
9. Add `organization-label`, `instance-of-organization`, and `organization-qid` columns; add `instance_of_add`, `authorized_label_add`, and `structured_value_add` columns; finalize workflow: [JSON][name_finalize]
10. Remove any facets and filters
11. Export full CSV from OpenRefine (retain file name)

[name_workflow]:      json/name/010-name-workflow.json
[name_recon_human]:   json/name/030-name-recon-human.json
[name_known_human_0]: json/name/040-name-known-human.json
[name_known_human_1]: json/name/041-name-known-human.json
[name_known_human_2]: json/name/042-name-known-human.json
[name_recon_org]:     json/name/060-name-recon-org.json
[name_known_org]:     json/name/070-name-known-org.json
[name_finalize]:      json/name/090-name-finalize.json

```
json/name/010-name-workflow.json
json/name/030-name-recon-human.json
json/name/040-name-known-human.json
json/name/041-name-known-human.json
json/name/042-name-known-human.json
json/name/050-name-recon-org.json
json/name/060-name-known-org.json
json/name/090-name-finalize.json
```
