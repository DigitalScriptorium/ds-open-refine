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
2. Known reconciliations (place):                                                            [JSON][place_known_names]
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
3. Use cluster and merge functions to standardize data values
4. Conduct known mass edits to clean and standardize values:                                 [JSON][mat_edits]
5. Manual mass edits to further standardize data values
6. Add new mass edits to known mass edits:                                                   [JSON][mat_edits]
7. Split and create column for reconciliation:                                               [JSON][mat_split]
8. Add AAT IDs (from controlled list), format, cleanup and rejoin:                           [JSON][mat_aat_merge_cleanup]

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

#### Reconciling genre terms from AAT

1. Copy `genre_as_recorded_aat` column for further evaluation:                               [JSON][genre_aat_split]
2. Conduct known mass edits to clean and standardize values:                                 [JSON][genre_aat_edits]
3. Use text facet tool to survey range of data values
4. Use cluster and merge functions to standardize data values
5. Manual mass edits to further standardize data values
6. Add new mass edits to known mass edits:                                                   [JSON][genre_aat_edits]
7. Run reconciliation:                                                                       [JSON][genre_aat_recon]
8. Known reconciliations (genre):                                                            [JSON][genre_aat_known]
9. Manual genre reconcilations
10. Add new genres to known genres:                                                          [JSON][genre_aat_known]
11. Add AAT IDs, format, cleanup and rejoin:                                                 [JSON][genre_aat_merge_cleanup]

[genre_aat_split]:          json/genre/aat/010-split_add_column.json
[genre_aat_edits]:          json/genre/aat/020-mass_edit.json
[genre_aat_recon]:          json/genre/aat/040-genre_recon.json
[genre_aat_known]:          json/genre/aat/050-genre_known.json
[genre_aat_merge_cleanup]:  json/genre/aat/090-format-aat-cleanup.json

```
json/genre/aat/010-split_add_column.json
json/genre/aat/020-mass_edit.json
json/genre/aat/040-genre_recon.json
json/genre/aat/050-genre_known.json
json/genre/aat/090-format-aat-cleanup.json
```

#### Reconciling genre terms from LoC to FAST

1. Copy `genre_as_recorded_lcsh` column for further evaluation:                              [JSON][genre_lc_split]
2. Conduct known mass edits to clean and standardize values:                                 [JSON][genre_lc_edits]
3. Use text facet tool to survey range of data values
4. Use cluster and merge functions to standardize data values
5. Manual mass edits to further standardize data values
6. Add new mass edits to known mass edits:                                                   [JSON][genre_lc_edits]
7. Run reconciliation:                                                                       [JSON][genre_lc_recon]
8. Known reconciliations (genre):                                                            [JSON][genre_lc_known]
9. Manual genre reconcilations
10. Add new genres to known genres:                                                          [JSON][genre_lc_known]
11. Add FAST IDs, format, cleanup and rejoin:                                                [JSON][genre_lc_merge_cleanup]

[genre_lc_split]:          json/genre/lc/010-split_add_column.json
[genre_lc_edits]:          json/genre/lc/020-mass_edit.json
[genre_lc_recon]:          json/genre/lc/040-genre_recon.json
[genre_lc_known]:          json/genre/lc/050-genre_known.json
[genre_lc_merge_cleanup]:  json/genre/lc/090-format-fast-cleanup.json

```
json/genre/lc/010-split_add_column.json
json/genre/lc/020-mass_edit.json
json/genre/lc/040-genre_recon.json
json/genre/lc/050-genre_known.json
json/genre/lc/090-format-fast-cleanup.json
```

### Reconciling subjects

#### Reconciling LCSH authorized headings and precoordinated terms with FAST equivalents

1. Copy, clean, and split `subject_as_recorded` column and set up reconciliation for subjects:                         [JSON][subject_split]
2. Known reconciliations (subject):                                                                                    [JSON][subject_known]
3. Manual subject reconciliations
4. Add new subjects to known subjects:                                                                                 [JSON][subject_known]
5. Add FAST IDs, split subject strings and set up reconciliation for first and second columns of subjects:             [JSON][subject_column1-2]
6. Known reconciliations (subject):                                                                                    [JSON][subject_known]
7. Manual subject reconciliations
8. Add new subjects to known subjects:                                                                                 [JSON][subject_known]
9. Add FAST IDs, set up reconciliation for first column of subjects:                                                   [JSON][subject_column1]
10. Known reconciliations (subject):                                                                                   [JSON][subject_known]

[subject_split]:            json/subject/010-split_add_column.json
[subject_known]:            json/subject/020-subject_known.json
[subject_column1-2]:        json/subject/030-add_first_second_column.json
[subject_column1]:          json/subject/040-recon_first_second_column.json

```
json/subject/010-split_add_column.json
json/subject/020-subject_known.json
json/subject/030-add_first_second_column.json
json/subject/040-add_first_column.json
```

*PLACEHOLDER FOR ADDITIONAL INSTRUCTIONS AS WORKFLOW PROGRESSES*

##### Reconciling LCSH terms to FAST topicals

2. Known subject reconciliations (topic):                                                                         [JSON][known_topic]
3. Manual topical subject reconciliations
4. Add new topical subjects to known topical subjects:                                                            [JSON][known_topic]
5. Add topical subject FAST IDs, set up reconciliation for geographic subjects:                                   [JSON][subject_add_topic_fast]

[known_topic]:              json/subject/topic/050-topic_known.json
[subject_add_topic_fast]:   json/subject/topic/090-format-topic-fast.json

```
json/subject/topic/050-topic_known.json
json/subject/topic/090-format-topic-fast.json
```

##### Reconciling LCSH terms to FAST geographics

6. Known subject reconciliations (geographic):                                                                    [JSON][known_geo]
7. Manual geographic subject reconciliations
8. Add new geographic subjects to known geographic subjects:                                                      [JSON][known_geo]
9. Add geographic subject FAST IDs, set up reconciliation for event subjects:                                     [JSON][subject_add_geo_fast]

[known_geo]:              json/subject/geo/050-geo_known.json
[subject_add_geo_fast]:   json/subject/geo/090-format-geo-fast.json

```
json/subject/geo/050-geo_known.json
json/subject/geo/090-format-geo-fast.json
```

##### Reconciling LCSH terms to FAST events

10. Known subject reconciliations (event):                                                                         [JSON][known_event]
11. Manual event subject reconciliations
12. Add new event subjects to known event subjects:                                                                [JSON][known_event]
13. Add event subject FAST IDs, set up reconciliation for personal name subjects:                                  [JSON][subject_add_event_fast]

[known_event]:              json/subject/event/050-event_known.json
[subject_add_event_fast]:   json/subject/event/090-format-event-fast.json

```
json/subject/event/050-event_known.json
json/subject/event/090-format-event-fast.json
```

##### Reconciling LCSH personal names to FAST personal names

14. Known subject reconciliation (personal names):                                                                 [JSON][known_pers]
15. Manual personal name subject reconciliations
16. Add new personal name subjects to known personal name subjects:                                                [JSON][known_pers]
17. Add personal name FAST IDs, set up reconciliation for corporate name subjects:                                 [JSON][subject_add_pers_fast]

[known_pers]:              json/subject/pers/050-pers_known.json
[subject_add_pers_fast]:   json/subject/pers/090-format-pers-fast.json

```
json/subject/pers/050-pers_known.json
json/subject/pers/090-format-pers-fast.json
```

##### Reconciling LCSH corporate names to FAST corporate names

18. Known subject reconciliation (corporate names):                                                                [JSON][known_corp]
19. Manual corporate name subject reconciliations
20. Add new corporate name subjects to known corporate name subjects:                                              [JSON][known_corp]
21. Add corporate name FAST IDs, set up reconciliation for form subjects:                                          [JSON][subject_add_corp_fast]

[known_corp]:              json/subject/corp/050-corp_known.json
[subject_add_corp_fast]:   json/subject/corp/090-format-corp-fast.json

```
json/subject/corp/050-corp_known.json
json/subject/corp/090-format-corp-fast.json
```

##### Reconciling LCSH form terms to FAST forms

18. Known subject reconciliation (form):                                                                           [JSON][known_form]
19. Manual form subject reconciliations
20. Add new form subjects to known form subjects:                                                                  [JSON][known_form]
21. Add form subject FAST IDs, set up reconciliation for form subjects:                                            [JSON][subject_add_form_fast]

[known_form]:              json/subject/form/050-form_known.json
[subject_add_form_fast]:   json/subject/form/090-format-form-fast.json

```
json/subject/form/050-form_known.json
json/subject/form/090-format-form-fast.json
```
