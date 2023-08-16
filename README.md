# Digital Scriptorium Data Reconciliation Process through OpenRefine

Digital Scriptorium OpenRefine documentation and JSON recipes for data reconciliation

Notes on editing file name variables (use all lowercase letters where applicable):
- DATE = the date the file/dataset was generated/created/extracted in `YYYYMMDD` format
- DATATYPE = the type of encoding standard or technical format of the metadata source, such as `marcxml` or `mets` or `csv`
- INSTITUTION = the code for the name of the institutional source for the data, such as `penn` or `kansas` or `csl`

## Reconciling names to Wikidata

1. Load `DATE-names-DATATYPE-INSTITUTION.csv` into OpenRefine; rename `DATE-names-DATATYPE-INSTITUTION-enriched.csv`
2. Add workflow columns: [JSON][name_workflow] (On the left, go to `Undo/Redo`, `Apply` and paste the JSON code)
3. Copy `name_as_recorded` column and reconcile new `recon-human` column against human type (Q5): [JSON][name_recon_human]
4. Apply list of previously reconciled or known human names: 0. [JSON][name_known_human_0], 1. [JSON][name_known_human_1], 2. [JSON][name_known_human_2]
5. Manually reconcile and update known human names: *edit [JSON][name_known_human_2]*
6. Add `human-label`, `instance-of-human`, and `human-qid` columns; rename reconciliation column to `recon-organization` to reconcile against organization type (Q43229): [JSON][name_recon_org]
7. Apply list of previously reconciled or known organization names: [JSON][name_known_org]
8. Manually reconcile and update known organization names: *edit [JSON][name_known_org]*
9. Add `organization-label`, `instance-of-organization`, and `organization-qid` columns; consolidate `authorized_label`, `instance_of`, and `structured_value` columns; finalize workflow: [JSON][name_finalize]
10. Do not forget to close all facets
11. Export three versions from OpenRefine as CSV files: 1) full document (retain file name), 2) facet by `structured_value` blank (null/empty) = `true` and rename it `DATE-names-DATATYPE-INSTITUTION-unreconciled.csv`, 3) facet by `structured_value` blank (null/empty) = `false` and rename it `DATE-names-DATATYPE-INSTITUTION-reconciled.csv`

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

## Reconciling places to TGN

1. Load `DATE-places-DATATYPE-INSTITUTION.csv` into OpenRefine; rename `DATE-places-DATATYPE-INSTITUTION.csv`
2. Add workflow columns: [JSON][place_workflow]
3. Copy `place_as_recorded` column and reconcile new `recon-place` column against TGN vocabulary: [JSON][place_recon]
4. Apply list of previously reconciled or known places: [JSON][place_known]
5. Manually reconcile and update known places: *edit [JSON][place_known]*
6. Consolidate `authorized_label` and `structured_value` columns; finalize workflow: [JSON][place_finalize]
7. Do not forget to close all facets
8. Export three versions from OpenRefine as CSV files: 1) full document (retain file name), 2) facet by `structured_value` blank (null/empty) = `true` and rename it `DATE-places-DATATYPE-INSTITUTION-unreconciled.csv`, 3) facet by `structured_value` blank (null/empty) = `false` and rename it `DATE-places-DATATYPE-INSTITUTION-reconciled.csv`

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

## Reconciling genres

1. Load `DATE-genres-DATATYPE-INSTITUTION.csv` into OpenRefine; rename `DATE-genres-DATATYPE-INSTITUTION-enriched.csv`
2. Add workflow columns: [JSON][genre_workflow]

[genre_workflow]: json/genre/010-genre-workflow.json

### to AAT

3. Copy filtered `genre_as_recorded` column and reconcile new `recon-genre` column against AAT vocabulary: [JSON][genre_aat_recon]
4. Apply list of previously reconciled or known AAT terms: [JSON][genre_aat_known]
5. Manually reconcile and update known AAT genre terms: *edit [JSON][genre_aat_known]*
6. Add `aat-label` and `genre-aat` columns: [JSON][genre_aat]

[genre_aat_recon]:   json/genre/aat/030-genre-aat-recon.json
[genre_aat_known]:   json/genre/aat/040-genre-aat-known.json
[genre_aat]:         json/genre/aat/050-genre-aat.json

### to FAST

3. Copy filtered `genre_as_recorded` column and reconcile new `recon-genre` column against FAST terms: [JSON][genre_fast_recon]
4. Apply list of previously reconciled or known FAST terms: [JSON][genre_fast_known]
5. Manually reconcile and update known FAST genre terms: *edit [JSON][genre_fast_known]*
6. Add `fast-label` and `genre-fast` columns: [JSON][genre_fast]

[genre_fast_recon]:   json/genre/fast/030-genre-fast-recon.json
[genre_fast_known]:   json/genre/fast/040-genre-fast-known.json
[genre_fast]:         json/genre/fast/050-genre-fast.json

#### *TBD instructions for other genres as needed*

### all genre terms: finalize

7. Finalize workflow; consolidate `authorized_label` and `structured_value` columns: [JSON][genre_finalize]
8. Export three versions from OpenRefine as CSV files: 1) full document (retain file name), 2) facet by `structured_value` blank (null/empty) = `true` and rename it `DATE-genres-DATATYPE-INSTITUTION-unreconciled.csv`, 3) facet by `structured_value` blank (null/empty) = `false` and rename it `DATE-genres-DATATYPE-INSTITUTION-reconciled.csv`

[genre_finalize]:    json/genre/090-genre-finalize.json

```
json/genre/010-genre-workflow.json
json/genre/aat/030-genre-aat-recon.json
json/genre/aat/040-genre-aat-known.json
json/genre/aat/050-genre-aat.json
json/genre/fast/030-genre-fast-recon.json
json/genre/fast/040-genre-fast-known.json
json/genre/fast/050-genre-fast.json
json/genre/090-genre-finalize.json
```

## Reconciling subjects to FAST

### Reconciling named subjects

1. Load `DATE-named-subjects-combined.csv` into OpenRefine; rename `DATE-named-subjects-combined-enriched.csv`
2. Add workflow columns: [JSON][subject_workflow]
3. Copy `subject_as_recorded` column and reconcile new `recon-subject` column against FAST terms: [JSON][named_subject_recon_1]
4. Apply list of previously reconciled or known FAST terms: [JSON][named_subject_known]
5. Manually reconcile and update known FAST terms: *edit [JSON][named_subject_known]*
6. Add `named-subject-label-1` and `named-subject-fast-1` columns, reconcile next `recon-subject` column: [JSON][named_subject_recon_2]
7. Apply list of previously reconciled or known FAST terms: [JSON][named_subject_known]
8. Manually reconcile and update known FAST terms: *edit [JSON][named_subject_known]*
9. Add `named-subject-label-2` and `named-subject-fast-2` columns; consolidate `authorized_label` and `structured_value` columns; finalize workflow: [JSON][named_subject_finalize]
10. Export three versions from OpenRefine as CSV files: 1) full document, 2) facet by `structured_value` blank (null/empty) = `true`, 3) facet by `structured_value` blank (null/empty) = `false`

[subject_workflow]:         json/subject/010-subject-workflow.json
[named_subject_recon_1]:    json/subject/named/030-named-subject-recon-1.json
[named_subject_known]:      json/subject/named/040-named-subject-known.json
[named_subject_recon_2]:    json/subject/named/060-named-subject-recon-2.json
[named_subject_finalize]:   json/subject/named/090-named-subject-finalize.json


### Reconciling subjects (topical, etc.)

1. Load `DATE-subjects-combined.csv` into OpenRefine; rename `DATE-subjects-combined-enriched.csv`
2. Add workflow columns: [JSON][subject_workflow]
3. Copy `subject_as_recorded` column and reconcile new `recon-subject` column against FAST terms: [JSON][subject_recon_1]
4. Apply list of previously reconciled or known FAST terms: [JSON][subject_known]
5. Manually reconcile and update known FAST terms: *edit [JSON][subject_known]*
6. Add `subject-label-1` and `subject-fast-1` columns, reconcile next `recon-subject` column: [JSON][subject_recon_2]
7. Apply list of previously reconciled or known FAST terms: [JSON][subject_known]
8. Manually reconcile and update known FAST terms: *edit [JSON][subject_known]*
9. Add `subject-label-2` and `subject-fast-2` columns, reconcile next `recon-subject` column: [JSON][subject_recon_3]
10. Apply list of previously reconciled or known FAST terms: [JSON][subject_known]
11. Manually reconcile and update known FAST terms: *edit [JSON][subject_known]*
12. Add `subject-label-3` and `subject-fast-3` columns; consolidate `authorized_label` and `structured_value` columns; finalize workflow: [JSON][subject_finalize]
13. Export three versions from OpenRefine as CSV files: 1) full document (retain file name), 2) facet by `structured_value` blank (null/empty) = `true` and rename it `DATE-subjects-DATATYPE-INSTITUTION-unreconciled.csv`, 3) facet by `structured_value` blank (null/empty) = `false` and rename it `DATE-subjects-DATATYPE-INSTITUTION-reconciled.csv`

[subject_recon_1]:    json/subject/topic/030-subject-recon-1.json
[subject_known]:      json/subject/topic/040-subject-known.json
[subject_recon_2]:    json/subject/topic/060-subject-recon-2.json
[subject_recon_3]:    json/subject/topic/090-subject-recon-3.json
[subject_finalize]:   json/subject/topic/120-subject-finalize.json

```
json/subject/010-subject-workflow.json
json/subject/named/030-named-subject-recon-1.json
json/subject/named/040-named-subject-known.json
json/subject/named/060-named-subject-recon-2.json
json/subject/named/090-named-subject-finalize.json
json/subject/topic/030-subject-recon-1.json
json/subject/topic/040-subject-known.json
json/subject/topic/060-subject-recon-2.json
json/subject/topic/090-subject-recon-3.json
json/subject/topic/120-subject-finalize.json
```

## Languages

[Language reconciliation instructions](/instructions/languages.md)


## Materials

[Material reconciliation instructions](/instructions/materials.md)

