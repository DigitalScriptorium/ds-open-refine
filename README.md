# Digital Scriptorium OpenRefine instructions and code

Digital Scriptorium OpenRefine documentation and code snippets

## Data reconciliation

### First: Add an index column

Create an index column:

- [`json/add_index_column.json`][add_index_column]

[add_index_column]:   json/add_index_column.json    "Add index column"

### Reconciling former owners

1. Split `former_owner_as_recorded` and set up reconciliation for owners:   [JSON][fo_split_owner]
2. Known name reconciliations (human):                                      [JSON][fo_known_names_human]
3. Manual human reconciliations
4. Add new human names to human known owners:                               [JSON][fo_known_names_human]
5. Add human QID column:                                                    [JSON][fo_add_human_qids]
6. Known name reconciliations (organization):                               [JSON][fo_known_names_orgn]
7. Manual organization reconciliations
8. Add new organization names to organization known owners:                 [JSON][fo_known_names_orgn]
9. Add organization QID column, clean up and rejoin records:                [JSON][fo_orgn_qids_merge_cleanup]

[fo_split_owner]:              json/former_owner/010-split_add_recon_column.json
[fo_known_names_human]:        json/former_owner/020-recon-known_names_human.json
[fo_add_human_qids]:           json/former_owner/050-human-qid-then-orgn-recon.json
[fo_known_names_orgn]:         json/former_owner/060-recon-known-names-organization.json
[fo_orgn_qids_merge_cleanup]:  json/former_owner/090-add-org-qids-cleanup-rejoin.json

### Reconciling authors

1. Split `author_as_recorded` and set up reconciliation for authors:        [JSON][author_split_owner]
2. Known name reconciliations (human):                                      [JSON][author_known_names_human]
3. Manual human reconciliations
4. Add new human names to human known owners:                               [JSON][author_known_names_human]
5. Add organization QID column, clean up and rejoin records:                [JSON][author_orgn_qids_merge_cleanup]

[author_split_owner]:              json/author/010-split_add_recon_column.json
[author_known_names_human]:        json/author/020-recon-known_names_human.json
[author_orgn_qids_merge_cleanup]:  json/author/050-cleanup-rejoin-records.json
