# Medical Billing & Coding Audit Framework

> **⚠️ Synthetic data:** The clinical encounter data referenced here is a de-identified, synthetic training dataset built for coursework purposes. No real patient records are used.

## Overview

This audit workflow takes AI-suggested ICD-10-CM and CPT codes for a set of clinical encounters, cross-checks them against the actual visit documentation, and produces a validated, correction-justified final coding table. The goal isn't "AI generates codes" — it's **AI proposes, documentation-grounded review disposes.**

## Audit & Validation Table

| Patient ID | Case | AI-Suggested Codes | Final Validated Codes | CPT Modifier | Issue Type & Justification |
|---|---|---|---|---|---|
| P001 | HTN & Hyperlipidemia Follow-up | ICD-10: I10, E78.5 · CPT: 99213 | ICD-10: I10, E78.5 · CPT: 99213 | None | No change needed — established visit, stable chronic conditions managed appropriately |
| P002 | Diabetes with Neuropathy & CKD | ICD-10: E11.9, N18.31 · CPT: 99213 | ICD-10: E11.40, G63, E11.22, N18.31, I10 · CPT: 99214 | None | More specific code needed — uncontrolled T2DM (A1c 8.2%), diabetic peripheral neuropathy, CKD stage 3a, and suboptimal HTN control were all documented but under-coded; complexity and 32-minute face-to-face time support 99214 |
| P003 | Lipoma Excision (Back, 2.8 cm) | ICD-10: D17.1 · CPT: 11403 | ICD-10: D17.1 · CPT: 11403 | None | No change needed — excised diameter (3.2 cm including margins) falls correctly within the CPT 11403 range (3.1–4.0 cm) |
| P004 | ED Chest Pain, GERD Diagnosis | ICD-10: R07.9 · CPT: 99284 | ICD-10: K21.9 · CPT: 99285 | 25 | More specific code needed — final diagnosis (GERD, ACS ruled out via serial troponins/EKG) plus high-complexity workup (EKG, labs, imaging, 4.5-hour observation) supports level-5 ED coding, not the symptom-only code originally suggested |
| P005 | Annual Exam with Same-Visit UTI | ICD-10: Z00.00, N39.0 · CPT: 99395, 99213 | ICD-10: Z00.00, N39.0 · CPT: 99395, 99213 | 25 | No change needed — preventive code plus problem-oriented code, correctly modified with -25 to indicate a significant, separately identifiable E/M service |

## Why This Matters for AI System Design

Two of five cases required correction — both in the direction of the AI *under-coding* relative to what the documentation actually supported. That's the operationally important finding: an AI-first coding pipeline without a validation layer doesn't just risk overbilling, it can just as easily leave legitimate revenue and accurate documentation on the table. The audit table format — AI suggestion next to validated final, with a mandatory justification column — is what makes the correction auditable rather than just asserted.
