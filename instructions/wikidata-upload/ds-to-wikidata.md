# Instructions for Using OpenRefine to Upload DS Data to Create Wikidata Items for Manuscripts

The following instructions are used to automate uploads of manuscript metadata from DS records in order to represent DS member collections in Wikidata using OpenRefine. Datasets are generated through use of the DS Wikibase Query Service using a [query template][query-template] to extract data that matches the DS-developed implementation of the [WikiProject Manuscripts data model][https://www.wikidata.org/wiki/Wikidata:WikiProject_Manuscripts/Data_Model].

## Preparing and Formatting DS Data for Reuse in Wikidata

1. Download input dataset to local machine and load input dataset into OpenRefine: [input datasets][inputs]
2. Clean and prepare columns for materials, centuries, places, and DS Wikibase item IDs (QIDs) by removing URI formatting, leaving DS QIDs: [JSON][prepare-dataset]
3. Split Wikidata-based columns from DS data (languages, scribes, artists, authors, owners) into separate columns: [JSON][split-wikidata-columns]
4. Load data dictionaries used for matching DS QIDs to Wikidata QIDS into OpenRefine; delete any previous versions from OpenRefine projects
  - [centuries][century-dictionary]
  - [languages][language-dictionary]
  - [materials][material-dictionary]
  - [places][place-dictionary]
  - [scripts][script-dictionary]
5. Match DS QID values for materials, centuries, places, and scripts to Wikidata QIDs using data dictionaries: [JSON][match-wikidata-values]
6. Run reconciliation to format dataset to create new Wikidata items: [JSON][new-wikidata-items]
7. Download the DS to Wikidata OpenRefine schema template to local machine: [Schema JSON file][schema-template]
8. Apply the DS to Wikidata schema template to the project by selecting `Extensions -> Wikibase` in the top right menu options, then `Manage schemas` and `Import new schema` to select the downloaded file
9. Review schema issues, resolve any missing or extra columns, and correct any invalid statement values 
10. For every `valueWikidata` column present, reconcile to Wikidata by clicking on the down arrow, selecting `Reconcile -> Use values as identifiers` and choose the `Wikidata reconci.link` option

## Matching Title Information to Wikidata Items

11. Run reconciliation process on title information: [JSON][title-wikidata-recon]
12. Review and make matches for title/work in Wikidata based on reconciliation information
13. If necessary, split columns and edit schema to include title/work (`titleWikidata`) and matching author information (`authorWikidata`) as qualifier(s) for `exemplar of` property statements

## Creating Wikidata Items for DS-Represented Manuscripts by Making Automated Edits

14. Review and resolve any additional schema issues prior to Wikibase edit/upload
15. Start process to push uploads to Wikidata by selecting `Extensions -> Wikibase` in the top right menu, then `Upload edits to Wikibase`
16. In the `summary` field, enter the input dataset filename formatted `YYYYMMDD-institutionCode-ds-wikidata` (e.g., `20250807-bec-ds-wikidata`)
17. Select `Upload edits`


[prepare-dataset]: 010-clean-prepare-dataset.json
[split-wikidata-columns]: 020-split-wikidata-based-columns.json
[match-wikidata-values]: 030-match-ds-to-wikidata-entities.json
[new-wikidata-items]: 040-reconcile-to-create-new-items.json
[title-wikidata-recon]: 050-reconcile-title-information.json

[query-template]: https://github.com/DigitalScriptorium/ds-data/blob/main/ds-to-wikidata/sparql-query-template
[inputs]: https://github.com/DigitalScriptorium/ds-data/tree/main/ds-to-wikidata/datasets/inputs
[schema-template]: https://github.com/DigitalScriptorium/ds-data/tree/main/ds-to-wikidata/wikibase-schemas/ds-to-wikibase-openrefine-schema-template.json

[century-dictionary]: https://github.com/DigitalScriptorium/ds-data/blob/main/ds-to-wikidata/crosswalks/entities/centuries-ds-aat-wikidata.csv
[language-dictionary]: https://github.com/DigitalScriptorium/ds-data/blob/main/ds-to-wikidata/crosswalks/entities/languages-ds-wikidata.csv
[material-dictionary]: https://github.com/DigitalScriptorium/ds-data/blob/main/ds-to-wikidata/crosswalks/entities/materials-ds-aat-wikidata.csv
[place-dictionary]: https://github.com/DigitalScriptorium/ds-data/blob/main/ds-to-wikidata/crosswalks/entities/places-ds-tgn-wikidata.csv
[script-dictionary]: https://github.com/DigitalScriptorium/ds-data/blob/main/ds-to-wikidata/crosswalks/entities/scripts-ds-aat-wikidata.csv
