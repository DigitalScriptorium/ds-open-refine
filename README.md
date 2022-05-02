# Digital Scriptorium Data Reconciliation Process through OpenRefine

Digital Scriptorium OpenRefine documentation and JSON recipes for data reconciliation

## Reconciling names to Wikidata

1. Load `DATE-names-combined.csv` into OpenRefine
2. Add workflow columns: [JSON][name_workflow]
3. Copy `name` column and reconcile new `recon-human` column against human type (Q5): [JSON][name_recon_human]
4. Apply list of previously reconciled or known human names: [JSON][name_known_human]
5. Add `qid` and `instance_of-human` columns; rename reconciliation column to `recon-organization` to reconcile against organization type (Q43229): [JSON][name_recon_org]
6. Apply list of previously reconciled or known organization names: [JSON][name_known_org]
7. Add `qid` and `instance_of-organization` columns; consolidate `instance_of` column; add `name_reconciled` column: [JSON][name_finalize]

[name_workflow]:    json/name/010-name-workflow.json
[name_recon_human]: json/name/030-name-recon-human.json
[name_known_human]: json/name/040-name-known-human.json
[name_recon_org]:   json/name/060-name-recon-org.json
[name_known_org]:   json/name/070-name-known-org.json
[name_finalize]:    json/name/090-name-finalize.json

```
json/name/010-name-workflow.json
json/name/030-name-recon-human.json
json/name/040-name-known-human.json
json/name/060-name-recon-org.json
json/name/070-name-known-org.json
json/name/090-name-finalize.json
```

## Reconciling places to TGN

1. Load `DATE-places-combined.csv` into OpenRefine
2. Add workflow columns: [JSON][place_workflow]
3. Copy `place` column and reconcile new `recon-place` column against TGN vocabulary: [JSON][place_recon]
4. Apply list of previously reconciled or known places: [JSON][place_known]
5. Add `place-tgn` column; add `place_reconciled` column: [JSON][place_finalize]

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

## Remainder TBD.
