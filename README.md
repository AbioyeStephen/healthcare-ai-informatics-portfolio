# AI in Healthcare & Medical Informatics — Portfolio

> **⚠️ Data disclaimer:** All patient cases, records, and identifying details in this repository are **synthetic, de-identified training exercise material** created for coursework purposes. No real patient information is included anywhere in this repo.

This repository documents applied AI prompt engineering and clinical informatics workflows completed as part of **AI in Healthcare: Practical Skills for Healthcare Professionals** (IBM SkillsBuild, Credential ID: `PLAN-81AB12E0256`).

It demonstrates how a clinical reasoning background (Doctor of Pharmacy training — diagnostic logic, constraint mapping, safety-critical protocols) translates directly into building **safe, audit-ready AI systems**: differential diagnosis support, patient-facing content generation with health-literacy constraints, and structured medical coding validation.

## Repository Structure

```text
healthcare-ai-informatics-portfolio/
│
├── README.md
├── docs/
│   ├── 01_differential_diagnosis_guide.md   — Structured clinical reasoning + AI safety guardrails
│   ├── 02_discharge_care_plan_ai.md         — Patient-facing AI content with literacy/safety constraints
│   └── 03_medical_billing_validation.md     — ICD-10-CM / CPT coding audit framework
└── data/
    └── sample_clinical_dataset_notes.md     — Notes on the synthetic dataset structure used for the audit
```

## What Each Piece Demonstrates

| Document | Core Skill Demonstrated |
|---|---|
| Differential Diagnosis Guide | Structuring AI output into audit-ready reasoning tables, forcing uncertainty disclosure, and building escalation rules that prevent an AI system from overstepping into unsafe territory |
| Discharge Care Plan | Prompt engineering for a defined audience (health literacy level, tone), while enforcing that every safety-critical parameter (allergies, dosages, red-flag symptoms) survives translation into plain language |
| Medical Billing Validation | Using AI to flag coding discrepancies against source documentation, then applying human validation — a real audit workflow, not just AI-generated output taken at face value |

The common thread across all three: **AI proposes, a defined constraint system verifies.** That's the same posture I bring to automation work generally — the AI can generate quickly, but the safety guardrails and validation layer are the actual engineering.

---
Curated and maintained by [Stephen](https://github.com/AbioyeStephen) · Pharm.D background · AI Automation Engineer
