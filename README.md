# Digital Scriptorium OpenRefine instructions and code

Digital Scriptorium OpenRefine documentation and code snippets

## Data reconciliation

### First: Add an index column

Create an index column:

- [`json/add_index_column.json`][add_index_column]

[add_index_column]:   json/add_index_column.json    "Add index column"

### Reconciling former owners

1. Split `former_owner_as_recorded` and set up reconciliation for owners:
    - [`json/former_owner-split_add_recon_column.json`][split_owner]
2. Perform known name reconciliations (human):
    - [`json/recon-known_names_human.json`][known_names]
3. Perform manual human reconciliations
4. Add human QID column:
    - [`json/recon-add_recon_column_qid-human.json`][add_reconned_qids]
5. Change recon type to organization:
    - [`json/recon-organization_recon.json`][orgn_recon]
6. Perform known name reconciliations (organization):
    - [`json/recon-known_names_organization.json`][known_names]
7. Perform manual organization reconciliations
8. Add organization QID column:
    - [`json/recon-add_recon_column_qid-orgn.json`][add_reconned_qids]
9. Merge human and organization QID columns:
    - [`json/recon-merge_human_orgn_qid_columns.json`][merge_qid_cols]
10. Remove Recon column, rejoin split cells:
    - [`json/former_owner-cleanup_rejoin_owners_and_qids.json`][cleanup_owner]


[split_owner]:        json/former_owner-split_add_recon_column.json           "Split owner and reconcile"
[known_names]:        json/recon-known_names_human.json                       "Known human name reconciliations"
[add_reconned_qids]:  json/recon-add_recon_column_qid-human.json              "Add human QID column for reconciliations"
[orgn_recon]:         json/recon-organization_recon.json                      "Start recon for type org"
[known_names_orgn]:   json/recon-known_names_organization.json                "Known organization name reconciliations"
[add_reconned_qids]:  json/recon-add_recon_column_qid-orgn.json               "Add organization QID column for reconciliations"
[merge_qid_cols]:     json/json/recon-merge_human_orgn_qid_columns.json       "Merge human, orgn QID columns"
[cleanup_owner]:      json/former_owner-cleanup_rejoin_owners_and_qids.json   "Cleanup and rejoin owners and QIDs"
