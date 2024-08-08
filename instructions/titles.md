## Reconciling titles

DS does not use a title authority file for title string reconciliation. Rather, a bespoke controlled vocabulary of Standard Titles has been developed over time to aggregate and harmonize the titles of works or texts represented in or by the metadata records of manuscript objects. Because we are not seeking to implement or reproduce a bibliocentric model, nor does the data we take in always support this kind representation, we are unable to provide metadata for Works in the bibliographic sense. Instead, Standard Titles offer the opportunity to enrich string values with our own authority values to better power faceted browsing, search, and retrieval.

To that end, we have made an evolving series of decisions to guide Standard Title creation and application (found below).

1. Examine the `title_as_recorded` and `uniform_title_as_recorded` fields. Determine if the title information can be standardized or if it is a specialized, unique, or highly descriptive title which does not lend itself to standardization and aggregation. *Not all titles can or should be standardized.*
2. Search in the [DS Catalog](https://catalog.digital-scriptorium.org/) or the [`title.csv` data dictionary](https://github.com/DigitalScriptorium/ds-data/blob/main/terms/reconciled/titles.csv) to see if a Standard Title has already been assigned to a similar title string.
3. If a Standard Title is unavailable, search in [Wikidata](https://wikidata.org/), or commonly used name or title Authority files or controlled vocabularies, such as [FAST](https://fast.oclc.org/searchfast/) or [LCNAF](https://id.loc.gov/authorities/names.html), to see if a suitable form of a title exists. Uniform title information from the original metadata, where available, may be helpful in determining how to standardize a title for enrichment.
4. Efforts should be made to aggregate works at the highest generic level possible. For instance:
    - "Book of Hours, use of Rome"
    - "Book of Hours : use of Rouen"
    - "Book of Hours, Use of Paris"<br>should all be assigned the Standard Title _Book of hours_
5. Standard Titles should be formatted in sentence case, with appropriate capitalization for proper nouns, unless convention/authorities dictate otherwise.
6. More than one Standard Title can be assigned to a title string. This should be done to represent as many works/texts/units as are represented in the original metadata. Examples include:
    - record with string value from `title_as_recorded`: "Bible, Gospel of John" should be assigned 2 Standard Title values: _Bible_;_Gospel of John_
    - record with string value from `title_as_recorded`: "Old Testament. Ezekiel, xix.12-xxxix.29" and string value from `uniform_title_as_recorded`: "Bible" should be assigned 3 Standard Title values: _Bible_;_Old testament_;_Book of Ezekiel_
7. When items have a well-known common or "trivial" name, assign that name as a Standard Title along with a more generic standard title, if applicable.
    - record with string value from `title_as_recorded`: "Llangatock Breviary" should be assigned 2 Standard Title values: _Llangatock Breviary_;_Breviary_
8. When the term "work" or "works" is used in reference to the production of particular authors or writers, the term "work(s)" should be retained:
    - e.g., string value "Collection of works by Saint Augustine" should be assigned a Standard Title of _Works of Augustine_
    - e.g., string value "Works of Aristotle, Theophrastus, Ammonius, Porphyrius, and Pseudo-Galen" should be assigned the following Standard Titles: _Works of Aristotle_;_Works of Theophrastus_;_Works of Ammonius_;_Works of Porphyrius_;_Works of Pseudo-Galen_
9. When a well-known or specific title is given, assign the Standard Title to reflect that text. An additional generic Standard Title may be assigned to facilitate retrieval.
    - e.g., string value "Opusculum astrologicum, ex diversorum libris, summa cura pro studiosorum utilitate collectum" should be assigned the following Standard Title: _Opusculum astrologicum_ and may be supplemented as described in cases below (_Astrological text_)
10. Defer to external sources for whether or not a Standard Title should be rendered in English or in another/original language.
    - e.g., string values "De coniuratione Catilinae" or "Bellum Catilinae" should be assigned the following Standard Title: _The Conspiracy of Catiline_
    - conversely, _Interpretationes nominum Hebraicorum_ is the preferred Standard Title for the text often translated as "Interpretation of Hebrew Names"
11. Spelling conventions should be standardized and modernized, unless convention/authorities dictate otherwise.
    - e.g., the Latin _Judeaos_ is preferred over "Iudeos" and the Spanish _Historia_ rather than "Hystoria"
13. When the terms "work" or "text" is used in reference to generic writings (no author represented), the term used should be "text":
    - e.g., string value "Collection of works on Arabic grammar" should be assigned a Standard Title of _Arabic grammatical texts_.
14. When a descriptive title is used in the `title_as_recorded` the singular or plural should be retained in the Standard Title, with each individual descriptor as a title:
    - e.g., string value "Astrological Miscellany" should be assigned a Standard Title of _Astrological texts_
    - e.g., string value "Medical treatise" should be assigned a Standard Title of _Medical text_
    - e.g., string value "Theological and legal works" should be assigned a Standard Title of _Theological texts_;_Legal texts_
15. When `title_as_recorded` is a commentary or other text written about a known work or body of work, the appropriate Standard Title should be used for such commentaries:
    - in the case of a named title within a single author's works, use the Standard Title _Commentary on..._, as in the example _Commentary on Aristotle_
    - in the case of biblical commentary, use the Standard Title _Bible commentary_ and _Commentary on..._, as in the examples _Commentary on John_ or _Commentary on Second Kings_
16. When `title_as_recorded` is a letter or letters, assign Standard Titles as follows:
    - in the case of a well-known letter or collection of letters, assign a Standard Title in accordance with convention/authority, as in _Letters of Phalaris_ or _Epistles of John_
    - in the case of a letter to well-known or specific individual or group, assign a Standard Title that begins with Letter(s) and which names the recipient of the letter, as in _Letter to Aurelius_ or _Letter to the Dominicans_
    - in the case of a letter that is not addressed to a well-known named individual or group (i.e., a more generic letter), assign the Standard Title _Letter_ or _Letters_



