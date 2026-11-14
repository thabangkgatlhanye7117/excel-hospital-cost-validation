# Hospital Cost Data Validation and Reconciliation (Excel)

A self-directed project that mirrors data capturer work: capturing, validating, reconciling and reporting on patient-level records. It uses a sample dataset of 500 hospital records (age, gender, length of stay, race, total charge, diagnosis group). It is a sample dataset, not live patient records.

## What the workbook does
- **Raw**: the original data, never edited.
- **Clean**: a working copy with six check columns (missing, duplicate, range, zero stay, high charge, overall).
- **Dictionary / Rules**: allowed values and the high-charge limit (Q3 + 1.5 x IQR).
- **Issues_Log**: every issue found, the action taken and why.
- **Reconciliation**: proves 500 raw records = 381 clean + 119 flagged, and that total charges (R1,387,194) match before and after.
- **Summary**: pivot table and chart of average charge by age band (clean records only).
- **Capture**: a data entry sheet with validation rules that block invalid entries.

## Findings
- Missing values: 1 (RACE)
- Possible duplicate rows: 43 (flagged, not deleted; no patient ID)
- Zero-day stays: 15 (flagged for review)
- High charges: 60 (flagged for review; costs are skewed)
- 119 of 500 records (24%) carry at least one flag. These are review flags, not confirmed errors.

## Limits
- No patient ID, so duplicates are only possible duplicates.
- The Summary excludes flagged records, so it understates typical cost (clean average about R1,737; all-record average about R2,774).
- The 1-4 age band has only 7 clean records, so its average is not reliable.

## Skills shown
Data validation, reconciliation, duplicate detection, COUNTIFS, pivot tables, data entry controls, documentation.