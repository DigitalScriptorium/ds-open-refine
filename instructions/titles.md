## Reconciling titles

DS does not use a title authority file for title string reconciliation. Rather, a bespoke controlled vocabulary of Standard Titles has been developed over time to aggregate and harmonize the titles of works or texts represented in or by the metadata records of manuscript objects. Because we are not seeking to implement or reproduce a bibliocentric model, nor does the data we take in always support this kind representation, we are unable to provide metadata for Works in the bibliographic sense. Instead, Standard Titles offer the opportunity to enrich string values with our own authority values to better power faceted browsing, search, and retrieval.

To that end, we have made an evolving series of decisions to guide Standard Title creation and application (found below).

1. Examine the `title_as_recorded` and `uniform_title_as_recorded` fields. Determine if the title information can be standardized or if it is a specialized, unique, or highly descriptive title which does not lend itself to standardization and aggregation.
2. Search in the [DS Catalog](https://catalog.digital-scriptorium.org/) or the [`title.csv` data dictionary](https://github.com/DigitalScriptorium/ds-data/blob/main/terms/reconciled/titles.csv) to see if a Standard Title has already been assigned to a similar title string.
3. If a Standard Title is unavailable, search in commonly used name or title Authority files or controlled vocabularies, such as LCNAF or FAST to see if a suitable form of a title. Uniform title information from the original metadata, where available, may be helpful in determining how to standardize a title for enrichment.
4. Efforts should be made to aggregate works at the highest generic level possible. For instance:
- "Book of Hours, use of Rome"
- "Book of Hours : use of Rouen"
- "Book of Hours, Use of Paris"
- "Hours of the Virgin"
should all be assigned the Standard Title "Book of hours"
5. Standard Titles should be formatted in sentence case, with appropriate capitalization for proper nouns.
6. More than one Standard Title can be assigned to a title string. This should be done to represent as many works/texts/units as are represented in the original metadata. Examples include:
- string value from `title_as_recorded`: "Bible, Gospel of John"
  -- should be assigned 2 Standard Title values: Bible;Gospel of John
- string value from `title_as_recorded`: "Old Testament. Ezekiel, xix.12-xxxix.29" | string value from `uniform_title_as_recorded`: "Bible"
  -- should be assigned 3 Standard Title values: Bible;Old testament;Ezekiel
7. TBD.
