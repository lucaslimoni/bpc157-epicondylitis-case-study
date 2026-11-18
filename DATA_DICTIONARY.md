# Data dictionary and interpretation

## data/observations.csv

- `date`: ISO 8601 observation date, blank when unspecified.
- `period`: baseline or follow-up period.
- `elbow`: participant-reported side(s), not independent diagnostic confirmation.
- `context`: circumstances of observation; nonmatched contexts must not be numerically compared as equivalent.
- `pain_min_0_10`, `pain_max_0_10`, `pain_point_0_10`: values on an explicit 0–10 scale **only**; blank when not assessed. The separately reported 0.05/100 is retained verbatim in notes, **not placed in a 0–10 field**.
- `measurement_type`: source/provenance.
- `warmup`, `training_status`, `adverse_events_reported`: descriptive fields; blank or "not assessed" is not proof of absence.
- `notes`: verbatim-like qualifications, uncertainty, and other contextual information.

## data/exposures.csv

- `date`: reporting/anchor date; does **not** imply an individually verified injection for every routine-report row.
- `administration_sequence`: reported sequence number only when known.
- `product_label`, `nominal_vial_mg`, `diluent`, `diluent_volume_ml`: reported label/preparation descriptors, **not chemical verification**.
- `route`, `site`, `reported_syringe_marking`, `reported_volume_ml`: participant-reported, with historical inconsistencies preserved and corrected in notes.
- `actual_volume_ml_verified`, `delivered_mg_verified`: blank because independent verification is unavailable.
- `identified_syringe`, `nominal_volume_for_reported_mark_ml`, `conditional_nominal_mg`: scale identification and conditional arithmetic only; **not prescribing guidance**.
- `verification_status`, `notes`: uncertainty and source metadata.

Do not use these records as a daily treatment log or clinical recommendation.

## data/laboratory_2026-11-11.csv

New longitudinal laboratory dataset: `analyte` (English machine-readable test identifier), `unit`, `previous_date`, `previous_value`, `current_date`, `current_value`, `lab_reference`, `source_pdf_page`, `source_type`, `notes`. Prior values are blank where the source report does not show a comparable 2026-09-16 result. One entry, `homa_ir_estimated`, is **derived** by fasting glucose (mg/dL) × fasting insulin (uIU/mL) / 405; it is not a directly measured laboratory analyte.

See [interpretation and limitations](data/lab_comparison_2026-09-16_2026-11-11.md). The source document is not uploaded because it contains directly identifying medical information. Comparisons do not prove medication effects, inflammation reduction or long-term safety.
