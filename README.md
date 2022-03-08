# Digital Scriptorium OpenRefine instructions and code

Digital Scriptorium OpenRefine documentation and code snippets

## Data reconciliation

### First: Add an index column

Create an index column:

- [`json/add_index_column.json`][add_index_column]

[add_index_column]:   json/add_index_column.json    "Add index column"

### Reconciling names

#### Reconciling authors

1. Copy and split `author_as_recorded` and set up reconciliation for human authors:          [JSON][author_split]
2. Known name reconciliations (human):                                                       [JSON][known_names_human]
3. Manual human reconciliations
4. Add new human names to human known authors:                                               [JSON][known_names_human]
5. Add human QID and instance_of columns, set up reconciliation for organizations:           [JSON][author_add_human_qids]
6. Known name reconciliations (organization):                                                [JSON][known_names_orgn]
7. Manual organization reconciliations
8. Add new organization names to organization known authors:                                 [JSON][known_names_orgn]
9. Add organization QID and instance_of columns, clean up and rejoin records:                [JSON][author_orgn_qids_merge_cleanup]

[author_split]:                    json/author/010-split_add_recon_column.json
[known_names_human]:               json/name/020-recon-known_names_human.json
[author_add_human_qids]:           json/author/050-human-qid-then-orgn-recon.json
[known_names_orgn]:                json/name/060-recon-known_names_organization.json
[author_orgn_qids_merge_cleanup]:  json/author/090-add-org-qids-cleanup-rejoin.json

```
json/author/010-split_add_recon_column.json
json/name/020-recon-known_names_human.json
json/author/050-human-qid-then-orgn-recon.json
json/name/060-recon-known_names_organization.json
json/author/090-add-org-qids-cleanup-rejoin.json
```

#### Reconciling artists

1. Copy and split `artist_as_recorded` and set up reconciliation for human artists:          [JSON][artist_split]
2. Known name reconciliations (human):                                                       [JSON][known_names_human]
3. Manual human reconciliations
4. Add new human names to human known artists:                                               [JSON][known_names_human]
5. Add human QID and instance_of columns, set up reconciliation for organizations:           [JSON][artist_add_human_qids]
6. Known name reconciliations (organization):                                                [JSON][known_names_orgn]
7. Manual organization reconciliations
8. Add new organization names to organization known artists:                                 [JSON][known_names_orgn]
9. Add organization QID and instance_of columns, clean up and rejoin records:                [JSON][artist_orgn_qids_merge_cleanup]

[artist_split]:                    json/artist/010-split_add_recon_column.json
[known_names_human]:               json/name/020-recon-known_names_human.json
[artist_add_human_qids]:           json/artist/050-human-qid-then-orgn-recon.json
[known_names_orgn]:                json/name/060-recon-known_names_organization.json
[artist_orgn_qids_merge_cleanup]:  json/artist/090-add-org-qids-cleanup-rejoin.json

```
json/artist/010-split_add_recon_column.json
json/name/020-recon-known_names_human.json
json/artist/050-human-qid-then-orgn-recon.json
json/name/060-recon-known_names_organization.json
json/artist/090-add-org-qids-cleanup-rejoin.json
```

#### Reconciling scribes

1. Copy and split `scribe_as_recorded` and set up reconciliation for human scribes:          [JSON][scribe_split]
2. Known name reconciliations (human):                                                       [JSON][known_names_human]
3. Manual human reconciliations
4. Add new human names to human known scribes:                                               [JSON][known_names_human]
5. Add human QID and instance_of columns, set up reconciliation for organizations:           [JSON][scribe_add_human_qids]
6. Known name reconciliations (organization):                                                [JSON][known_names_orgn]
7. Manual organization reconciliations
8. Add new organization names to organization known scribes:                                 [JSON][known_names_orgn]
9. Add organization QID and instance_of columns, clean up and rejoin records:                [JSON][scribe_orgn_qids_merge_cleanup]

[scribe_split]:                    json/scribe/010-split_add_recon_column.json
[known_names_human]:               json/name/020-recon-known_names_human.json
[scribe_add_human_qids]:           json/scribe/050-human-qid-then-orgn-recon.json
[known_names_orgn]:                json/name/060-recon-known_names_organization.json
[scribe_orgn_qids_merge_cleanup]:  json/scribe/090-add-org-qids-cleanup-rejoin.json

```
json/scribe/010-split_add_recon_column.json
json/name/020-recon-known_names_human.json
json/scribe/050-human-qid-then-orgn-recon.json
json/name/060-recon-known_names_organization.json
json/scribe/090-add-org-qids-cleanup-rejoin.json
```

#### Reconciling former owners

1. Copy and split `former_owner_as_recorded` and set up reconciliation for human owners:     [JSON][fo_split]
2. Known name reconciliations (human):                                                       [JSON][known_names_human]
3. Manual human reconciliations
4. Add new human names to human known owners:                                                [JSON][known_names_human]
5. Add human QID and instance_of columns, set up reconciliation for organizations:           [JSON][fo_add_human_qids]
6. Known name reconciliations (organization):                                                [JSON][known_names_orgn]
7. Manual organization reconciliations
8. Add new organization names to organization known owners:                                  [JSON][known_names_orgn]
9. Add organization QID and instance_of columns, clean up and rejoin records:                [JSON][fo_orgn_qids_merge_cleanup]

[fo_split]:                    json/former_owner/010-split_add_recon_column.json
[known_names_human]:           json/name/020-recon-known_names_human.json
[fo_add_human_qids]:           json/former_owner/050-human-qid-then-orgn-recon.json
[known_names_orgn]:            json/name/060-recon-known_names_organization.json
[fo_orgn_qids_merge_cleanup]:  json/former_owner/090-add-org-qids-cleanup-rejoin.json

```
json/former_owner/010-split_add_recon_column.json
json/name/020-recon-known_names_human.json
json/former_owner/050-human-qid-then-orgn-recon.json
json/name/060-recon-known_names_organization.json
json/former_owner/090-add-org-qids-cleanup-rejoin.json
```

### Reconciling places

1. Copy, split, and clean `production_place_as_recorded` column and set up reconciliation:   [JSON][place_split]
2. Known name reconciliations (place):                                                       [JSON][place_known_names]
3. Manual place reconciliations
4. Add new place names to known place names:                                                 [JSON][place_known_names]
5. Add TGN IDs, format, cleanup and rejoin:                                                  [JSON][place_tgn_merge_cleanup]

[place_split]:              json/place/010-clean_split_add_recon_column.json
[place_known_names]:        json/place/020-recon-known_names_place.json
[place_tgn_merge_cleanup]:  json/place/090-format-tgn-cleanup.json

```
json/place/010-clean_split_add_recon_column.json
json/place/020-recon-known_names_place.json
json/place/090-format-tgn-cleanup.json
```

### Reconciling languages

1. Copy, split, and clean `language_as_recorded` column and set up reconciliation:           [JSON][lang_split]
2. Known reconciliations (language):                                                         [JSON][lang_known]
3. Manual language reconciliations
4. Add new languages to known languages:                                                     [JSON][lang_known]
5. Add ISO 369-3 codes, cleanup and rejoin:                                                  [JSON][lang_iso_merge_cleanup]

[lang_split]:              json/language/010-clean_split_add_recon_column.json
[lang_known]:              json/language/020-recon-known_lang.json
[lang_iso_merge_cleanup]:  json/language/090-format-iso-cleanup.json

```
json/language/010-clean_split_add_recon_column.json
json/language/020-recon-known_lang.json
json/language/090-format-iso-cleanup.json
```

### Reconciling materials

1. Copy and clean `material_placeholder` column for further evaluation:                      [JSON][mat_copy_clean]
2. Use text facet tool to survey range of data values
4. Use cluster and merge functions to standardize data values
5. Conduct known mass edits to clean and standardize values:                                 [JSON][mat_edits]
6. Manual mass edits to further standardize data values
7. Add new mass edits to known mass edits:                                                   [JSON][mat_edits]
8. Split and create column for reconciliation:                                               [JSON][mat_split]
9. Add AAT IDs (from controlled list), format, cleanup and rejoin:                           [JSON][mat_aat_merge_cleanup]

[mat_copy_clean]:          json/material/010-clean_add_column.json
[mat_edits]:               json/material/030-mass_edit.json
[mat_split]:               json/material/050-split_add_recon_column.json
[mat_aat_merge_cleanup]:   json/material/090-format-aat-cleanup.json

```
json/material/010-clean_add_column.json
json/material/030-mass_edit.json
json/material/050-split_add_recon_column.json
json/material/090-format-aat-cleanup.json
```

### Reconciling genres

1. Copy and clean `genre_as_recorded` column for further evaluation:                         [JSON][genre_copy_clean]
2. Use text facet tool to survey range of data values
4. Use cluster and merge functions to standardize data values
5. Conduct known mass edits to clean and standardize values:                                 [JSON][genre_edits]
6. Manual mass edits to further standardize data values
7. Add new mass edits to known mass edits:                                                   [JSON][genre_edits]
8. Split and create column for reconciliation:                                               [JSON][genre_split]
9. Known reconciliations (genre):                                                            [JSON][genre_known]
10. Manual genre reconcilations
11. Add new genres to known genres:                                                          [JSON][genre_known]
12. Add AAT IDs, format, cleanup and rejoin:                                                 [JSON][genre_aat_merge_cleanup]

[genre_copy_clean]:          json/genre/010-clean_add_column.json
[genre_edits]:               json/genre/020-mass_edit.json
[genre_split]:               json/genre/040-split_add_recon_column.json
[genre_known]:               json/genre/050-genre_known.json
[genre_aat_merge_cleanup]:   json/genre/090-format-aat-cleanup.json

```
json/genre/010-clean_add_column.json
json/genre/020-mass_edit.json
json/genre/040-split_add_recon_column.json
json/genre/050-genre_known.json
json/genre/090-format-aat-cleanup.json
```
