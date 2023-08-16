## Reconciling genres

1. Load `DATE-genres-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-genres-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][genre_workflow]

[genre_workflow]: json/genre/010-genre-workflow.json

### to AAT

3. Copy filtered `genre_as_recorded` column and reconcile new `recon-genre` column against AAT vocabulary: [JSON][genre_aat_recon]
4. Apply list of previously reconciled or known AAT terms: [JSON][genre_aat_known]
5. Manually reconcile and update known AAT genre terms: *edit [JSON][genre_aat_known] and submit pull request*
6. Add `aat-label` and `genre-aat` columns: [JSON][genre_aat]

[genre_aat_recon]:   json/genre/aat/030-genre-aat-recon.json
[genre_aat_known]:   json/genre/aat/040-genre-aat-known.json
[genre_aat]:         json/genre/aat/050-genre-aat.json

### to FAST

3. Copy filtered `genre_as_recorded` column and reconcile new `recon-genre` column against FAST terms: [JSON][genre_fast_recon]
4. Apply list of previously reconciled or known FAST terms: [JSON][genre_fast_known]
5. Manually reconcile and update known FAST genre terms: *edit [JSON][genre_fast_known] and submit pull request*
6. Add `fast-label` and `genre-fast` columns: [JSON][genre_fast]

[genre_fast_recon]:   json/genre/fast/030-genre-fast-recon.json
[genre_fast_known]:   json/genre/fast/040-genre-fast-known.json
[genre_fast]:         json/genre/fast/050-genre-fast.json

#### *TBD instructions for other genres as needed*

### all genre terms: finalize

7. Finalize workflow; add `authorized_label_add` and `structured_value_add` columns: [JSON][genre_finalize]
8. Remove any facets and filters
9. Export full CSV file (retain file name)

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
