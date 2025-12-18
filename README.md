# Digital Scriptorium Data Reconciliation Process through OpenRefine

Digital Scriptorium (DS) OpenRefine documentation and JSON recipes for data reconciliation and management

## Data reconciliation and semantic enrichment

DS aggregates, harmonizes, enriches, transforms, and republishes institutional metadata about pre- and early modern manuscript objects in North American collections to build and grow a national union catalog. The result of this work is the DS Catalog, which renders previously siloed institutional data into linked open data (LOD) stored in a free and open Wikibase database. Member institutions help build this national union catalog through contributions of their metadata records describing manuscripts in their collections. DS enhances the data and makes it more powerful through semantic enrichment, linking relatively unstructured or semi-structured "as recorded" data in manuscript records to LOD vocabularies and authorities. The enrichment process helps to better standardize and align heterogeneous metadata supplied from disparate institutions so that it can be searched in a single interface, adding significant value to the data in two ways. First, semantic enrichment powers robust faceted browsing and searching as well as the ability to query linked data using SPARQL, which allows users to search across previously siloed collections that originally used different data encoding standards. Second, enrichment and transformation increases the linkability of data in manuscript records by connecting them to other linked data, thus making institutional data more valuable and reusable.

When structured data is contributed by a member institution, this data is extracted for both data reconciliation (recon-extraction) and generation of a spreadsheet used to import records into the DS Wikibase (import generation). Recon-extraction begins the semantic enrichment process by using DS-designed software to isolate unique data values occurring in the structured institutional data for metadata elements which will be enriched by DS staff prior to upload in the DS Catalog. These data values, based on the DS data model, are
- genres
- languages
- materials
- names
- places
- subjects
- titles

During recon-extraction, data values in institutional ("as recorded") data are compared against existing data dictionaries (by metadata element) which includes all data values previously encountered. Recon-extraction matches existing reconciliations automatically with authority records in the Wikibase. Recon-extraction results in spreadsheets for each metadata element created from extracted data and showing both reconciled and unreconciled values from a dataset. For unreconciled data, DS staff undertake data reconciliation to match unreconciled values with their equivalents in designated LOD authorities and vocabularies, such as Wikidata, OCLC Faceted Application of Subject Terminology (FAST), and the Getty Vocabularies. Once newly encountered values have been reconciled, the data dictionaries are updated with the new reconciliations. This means that on future processing of the data, these reconciliations will be automatically captured, allowing data to be automatically enriched prior to upload. Enriched data is generated and stored temporarily in an import spreadsheet which is pushed to the DS Wikibase to create DS records.

## General instructions for processing data

The following instructions discuss management, handling, and processing of recon-extraction spreadsheets through the naming of files, discussion of the manual steps of the reconciliation process, and JSON recipes for automating reconciliation tasks using OpenRefine.

### File naming conventions

Recon-extraction spreadsheets should be carefully named to track their source, their type, and date of contribution. This allows data to be properly archived and to follow up on workflow issues such as errors and discrepancies.

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

When utilizing the JSON instructions (also known as recipes) found in this repository for DS data in OpenRefine, find the left column, select the `Undo/Redo` tab, select `Apply`, paste the JSON code, and then select `Perform operations`. This will execute the prewritten commands which perform various actions on the data for the reconciliation process and when merging new datasets with previous ones.

Facets and filters can also be used on the data by using drop-down menus available on each column header and displayed in the left column when selecting the `Facet/Filter` tab.

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

### Instructions for Uploading DS data to Wikidata

[Processing DS data to represent manuscript objects in Wikidata](instructions/wikidata-upload/ds-to-wikidata.md)
