# Digital Scriptorium OpenRefine instructions and code

Digital Scriptorium OpenRefine documentation and code snippets

1. Create an index column:
    - [`json/add_index_column.json`][add_index_column]
2. Split `former_owner_as_recorded` and set up reconciliation for owners:
    - [`json/former_owner-cleanup_rejoin_owners_and_qids.json`][split_owner]
3. Perform known name reconciliations:
    - [`json/recon-know_names.json`][known_names]
4. Perform known extra reconciliations
5. Add QID column:
    - [`json/recon-add_recon_column_quids.json`][add_reconned_qids]
6. Remove Recon column, rejoin split cells:
    - [`json/former_owner-cleanup_rejoin_owners_and_qids.json`][clean_owner]


[add_index_column]:   json/add_index_column.json                              "Add index column"
[split_owner]:        json/former_owner-cleanup_rejoin_owners_and_qids.json  "Split owner and reconcile"
[known_names]:        json/recon-know_names.json                              "Known name reconciliations"
[add_reconned_qids]:  json/recon-add_recon_column_quids.json                  "Add QID column for reconciliations"
[clean_owner]:        json/former_owner-cleanup_rejoin_owners_and_qids.json   "Cleanup and rejoin owners and QIDs"

