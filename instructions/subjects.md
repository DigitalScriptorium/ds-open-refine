## Reconciling subjects to FAST based on MARC data

Special note for this process: When manually reconciling and updating JSON instructions to add additional "known" subjects, retain those JSON instructions and update at the end of the process. Creating multiple pull requests branched from the same file will create multiple conflicts and prevent merging of JSON instructions.

### Reconciling subjects of any type

1. Load `DATE-named-subjects-INSTITUTION-DATATYPE.csv` OR `DATE-subjects-INSTITUTION-DATATYPE.csv` into OpenRefine; rename `DATE-named-subjects-INSTITUTION-DATATYPE-enriched.csv` OR `DATE-subjects-INSTITUTION-DATATYPE-enriched.csv`
2. Add workflow columns: [JSON][subject_workflow]
3. Copy `subject_as_recorded` column and reconcile new `recon-subject` column against FAST terms: [JSON][subject_recon_1]
4. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
5. Manually reconcile and extract known FAST terms, retain for update at the end of the process
6. Add `subject-label-1` and `subject-id-1` columns, reconcile next `recon-subject` column: [JSON][subject_recon_2]
7. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
8. Manually reconcile and extract known FAST terms, retain for update at the end of the process
9. Add `subject-label-2` and `subject-id-2` columns; consolidate `subject-label-1-2` and `subject-id-1-2` columns; reconcile next `recon-subject` column: [JSON][subject_recon_3]
10. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
11. Manually reconcile and extract known FAST terms, retain for update at the end of the process
12. Add `subject-label-3` and `subject-id-3` columns; consolidate `subject-label-1-2-3` and `subject-id-1-2-3` columns; reconcile next `recon-subject` column: [JSON][subject_recon_4]
13. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
14. Manually reconcile and extract known FAST terms, retain for update at the end of the process
15. Add `subject-label-4` and `subject-id-4` columns; reconcile next `recon-subject` column: [JSON][subject_recon_5a]
16. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
17. Manually reconcile and extract known FAST terms, retain for update at the end of the process
18. Add `subject-label-5a` and `subject-id-5a` columns; reconcile next `recon-subject` column: [JSON][subject_recon_5b]
19. Apply list of previously reconciled or known FAST terms: [Form Terms JSON][subject_form_known]
20. Manually reconcile and extract known FAST terms, retain for update at the end of the process
21. Add `subject-label-5b` and `subject-id-5b` columns; consolidate `subject-label-4-5` and `subject-id-4-5` columns; reconcile next `recon-subject` column: [JSON][subject_recon_6]
22. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
23. Manually reconcile and extract known FAST terms, retain for update at the end of the process
24. Add `subject-label-6` and `subject-id-6` columns; reconcile next `recon-subject` column: [JSON][subject_recon_7a]
25. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
26. Manually reconcile and extract known FAST terms, retain for update at the end of the process
27. Add `subject-label-7a` and `subject-id-7a` columns; reconcile next `recon-subject` column: [JSON][subject_recon_7b]
28. Apply list of previously reconciled or known FAST terms: [Form Terms JSON][subject_form_known]
29. Manually reconcile and extract known FAST terms, retain for update at the end of the process
30. Add `subject-label-7b` and `subject-id-7b` columns; consolidate `subject-label-6-7` and `subject-id-6-7` columns; reconcile next `recon-subject` column: [JSON][subject_recon_8]
31. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
32. Manually reconcile and extract known FAST terms, retain for update at the end of the process
33. Add `subject-label-8` and `subject-id-8` columns; reconcile next `recon-subject` column: [JSON][subject_recon_9a]
34. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
35. Manually reconcile and extract known FAST terms, retain for update at the end of the process
36. Add `subject-label-9a` and `subject-id-9a` columns; reconcile next `recon-subject` column: [JSON][subject_recon_9b]
37. Apply list of previously reconciled or known FAST terms: [Form Terms JSON][subject_form_known]
38. Manually reconcile and extract known FAST terms, retain for update at the end of the process
39. Add `subject-label-9b` and `subject-id-9b` columns; consolidate `subject-label-8-9` and `subject-id-8-9` columns; reconcile next `recon-subject` column: [JSON][subject_recon_10a]
40. Apply list of previously reconciled or known FAST terms: [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known]
41. Manually reconcile and extract known FAST terms, retain for update at the end of the process
42. Add `subject-label-9a` and `subject-id-9a` columns; reconcile next `recon-subject` column: [JSON][subject_recon_10b]
43. Apply list of previously reconciled or known FAST terms: [Form Terms JSON][subject_form_known]
44. Manually reconcile and update known FAST terms: *edit [Named Subjects JSON][named_subject_known] OR [Subjects JSON][subject_known] AND [Form Terms JSON][subject_form_known] and submit pull requests*
45. Add `subject-label-10b` and `subject-id-10b` columns; consolidate all columns into `authorized_label_add` and `structured_value_add`; finalize workflow: [JSON][subject_finalize]
46. Remove any facets and filters
47. Export full CSV from OpenRefine (retain file name)


[subject_workflow]:       json/subject/010-subject-workflow.json
[subject_recon_1]:        json/subject/030-subject-recon-1.json
[subject_known]:          json/subject/040-subject-known.json
[named_subject_known]:    json/subject/040-named-subject-known.json
[subject_recon_2]:        json/subject/060-subject-recon-2.json
[subject_recon_3]:        json/subject/090-subject-recon-3.json
[subject_recon_4]:        json/subject/120-subject-recon-4.json
[subject_recon_5a]:       json/subject/150-subject-recon-5a.json
[subject_recon_5b]:       json/subject/180-subject-recon-5b.json
[subject_form_known]:     json/subject/190-subject-form-known.json
[subject_recon_6]:        json/subject/210-subject-recon-6.json
[subject_recon_7a]:       json/subject/240-subject-recon-7a.json
[subject_recon_7b]:       json/subject/270-subject-recon-7b.json
[subject_recon_8]:        json/subject/300-subject-recon-8.json
[subject_recon_9a]:       json/subject/330-subject-recon-9a.json
[subject_recon_9b]:       json/subject/360-subject-recon-9b.json
[subject_recon_10a]:      json/subject/390-subject-recon-10a.json
[subject_recon_10b]:      json/subject/420-subject-recon-10b.json
[subject_finalize]:       json/subject/450-subject-finalize.json

```
json/subject/010-subject-workflow.json
json/subject/030-subject-recon-1.json
json/subject/040-subject-known.json
json/subject/040-named-subject-known.json
json/subject/060-subject-recon-2.json
json/subject/090-subject-recon-3.json
json/subject/120-subject-recon-4.json
json/subject/150-subject-recon-5a.json
json/subject/180-subject-recon-5b.json
json/subject/190-subject-form-known.json
json/subject/210-subject-recon-6.json
json/subject/240-subject-recon-7a.json
json/subject/270-subject-recon-7b.json
json/subject/300-subject-recon-8.json
json/subject/330-subject-recon-9a.json
json/subject/360-subject-recon-9b.json
json/subject/390-subject-recon-10a.json
json/subject/420-subject-recon-10b.json
json/subject/450-subject-finalize.json
```
