# Digital Scriptorium OpenRefine instructions and code

Digital Scriptorium OpenRefine documentation and code snippets

## Data reconciliation

### First: Add an index column

Create an index column:

- [`json/add_index_column.json`][add_index_column]

[add_index_column]:   json/add_index_column.json    "Add index column"

### Reconciling former owners

1. Split `former_owner_as_recorded` and set up reconciliation for owners:
    - [JSON][split_owner]
2. Perform known name reconciliations (human):
    - [JSON][known_names]
3. Perform manual human reconciliations
4. Add human QID column:
    - [JSON][add_human_qids]
5. Perform known name reconciliations (organization):
    - [JSON][known_names_orgn]
6. Perform manual organization reconciliations
7. Add organization QID column:
    - [JSON][orgn_qids_merge_cleanup]


## Old steps

9. Merge human and organization QID columns:
    - [JSON][merge_qid_cols]
10. Remove Recon column, rejoin split cells:
    - [JSON][cleanup_owner]


[split_owner]:              json/former_owner/010-split_add_recon_column.json       "Split owner and reconcile"
[known_names]:              json/names/recon-known_names_human.json                 "Known human name reconciliations"
[add_human_qids]:           json/former_owner/040-human-qid-then-orgn-recon.json    "Add human QID column for reconciliations"
[orgn_recon]:               json/recon-organization_recon.json                      "Start recon for type org"
[known_names_orgn]:         json/names/recon-known_names_organization.json          "Known organization name reconciliations"
[orgn_qids_merge_cleanup]:  json/former_owner/070-add-org-qids-cleanup-rejoin.json  "Add organization QID column for reconciliations"


[merge_qid_cols]:           json/recon-merge_human_orgn_qid_columns.json            "Merge human, orgn QID columns"
[cleanup_owner]:            json/former_owner-cleanup_rejoin_owners_and_qids.json   "Cleanup and rejoin owners and QIDs"
