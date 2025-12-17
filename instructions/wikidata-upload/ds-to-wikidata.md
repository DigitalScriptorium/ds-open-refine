# TBD.

1. Load input dataset into OpenRefine
2. Clean and prepare columns for materials, centuries, places, and DS Wikibase item IDs (QIDs) by removing URI formatting, leaving DS QIDs.
3. Split Wikidata-based columns (languages, scribes, artists, authors, owners) into separate columns: [JSON]
4. Load data dictionaries used for matching DS QIDs to Wikidata QIDS into OpenRefine. (Delete any previous versions from existing OpenRefine projects.)
  - fdljfdlj
  - dsahfkjhfds
  - dkjhdkjhf
  - fdkjhfkjhfds
5. Match DS QID values for materials, centuries, places, and scripts to Wikidata QIDs using data dictionaries: [JSON]
6. Run reconciliation to format dataset to create new Wikidata items: [JSON] 
7. Apply the DS to Wikidata schema template to prepare for upload
8. Review schema issues, resolve any missing or extra columns, and correct any invalid statement values 
9. For every `valueWikidata` column present, reconcile to Wikidata by clicking on the down arrow, selecting `Reconcile -> Use values as identifiers` and choose the `Wikidata reconci.link` option
10. Run reconciliation process on title information: [JSON]
11. Review and make matches for title/work in Wikidata based on reconciliation information
12. Edit schema to include title/work (`titleWikidata`) and matching author information (`authorWikidata`) as qualifier(s) for `exemplar of` property statements 
13. Review and resolve any additional schema issues prior to Wikibase edit

