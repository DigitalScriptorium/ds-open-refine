# Digital Scriptorium Data Reconciliation Process through OpenRefine

Digital Scriptorium OpenRefine documentation and JSON recipes for data reconciliation and management

## General instructions

### File naming conventions

When utilizing the JSON instructions (also known as recipes) found in this repository for DS data in OpenRefine, find the left column, select the `Undo/Redo` tab, select `Apply`, paste the JSON code, and then select `Perform operations`. This will execute the prewritten commands which perform various actions on the data for the reconciliation process and when merging new datasets with previous ones.

Facets and filters can also be used on the data by using drop-down menus available on each column header and displayed in the left column when selecting the `Facet/Filter` tab.

The following notes apply to file naming conventions for editing file name variables found in the [instructions in this repository](/instructions/) (use all lowercase letters where applicable):
- DATE = the date the file/dataset was generated/created/extracted in `YYYYMMDD` format
- VALUE = the type of metadata values or metadata element extracted and enriched, such as `genres` or `languages` or `names` 
- INSTITUTION = the code for the name of the institutional source for the data, such as `penn` or `kansas` or `csl`
- DATATYPE = the type of encoding standard or technical format of the metadata source, such as `marcxml` or `mets` or `csv`
- One or more DIFFERENTIATORS may also be added on the file name to disambiguate files, using sources names of collections or databases, such as `bibliophilly` or `muslimworld`, or batch numbers, such as `batch-1`, `batch-2`, etc.

Examples of correctly formatted file names:
- `20230518-materials-rome-mets-legacy-enriched.csv`
- `20230630-genres-penn-marcxml-bibliophilly-enriched.csv`
- `20230715-names-kansas-marc-enriched.csv`
- `20230816-languages-princeton-marcxml-batch-3-enriched.csv`
- `20230901-places-hrc-csv-fragments-batch-1-enriched.csv`

### Manual reconciliation
TBD.

### Automated reconciliation instructions by metadata element / authority type
Introductory text?

#### Genres

[Genre reconciliation instructions](/instructions/genres.md)

#### Languages

[Language reconciliation instructions](/instructions/languages.md)

#### Materials

[Material reconciliation instructions](/instructions/materials.md)

#### Names

[Name reconciliation instructions](/instructions/names.md)

#### Places

[Place reconciliation instructions](/instructions/places.md)

#### Subjects

[Subject reconciliation instructions](/instructions/subjects.md)

#### Titles

[Title reconciliation instructions](instructions/titles.md)

### Instructions for integrating new reconciliations with previously reconciled data

[Merging newly enriched data with data dictionaries](instructions/merge-new-data.md)
