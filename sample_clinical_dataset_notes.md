# Sample Clinical Dataset — Structure Notes

> **⚠️ Synthetic data:** This dataset is de-identified, synthetic training material created for coursework purposes. No real patient records are included.

The billing audit in `docs/03_medical_billing_validation.md` was built against a small synthetic dataset of five clinical encounters, structured as one row per patient with the following columns:

- `Patient ID`
- `Case`
- `Patient information`
- `Visit setting`
- `Visit details`
- `Procedure details`
- `PMH` (past medical history)
- `Medications`
- `Vitals / exams`
- `Assessment`
- `Plan`
- `Total face-to-face time`
- `Referrals`

Each row represents a distinct visit type — a chronic disease follow-up, a same-day procedure, an ED presentation, and a preventive exam with an incidental acute finding — chosen to exercise different coding scenarios (established visit, procedure coding, high-acuity ED coding, and modifier-25 dual coding) rather than to represent any real patient population.
