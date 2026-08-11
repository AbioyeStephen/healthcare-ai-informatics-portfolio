# Differential Diagnosis Guide & AI Safety Reasoning

> **⚠️ Synthetic case:** The patient case below is a fictional training exercise scenario. No real patient data is used.

## 1. Clinical Case Overview

- **Patient:** 52-year-old female presenting with a 3-week history of fatigue, symmetrical joint pain (hands and knees), malar rash (cheeks and nasal bridge), occasional non-radiating chest pain, and low-grade fever (99.8°F / 37.7°C).
- **Initial Labs & Vitals:** Low WBC count (immune dysregulation), mildly reduced hemoglobin (mild anemia), elevated CRP and ESR (active systemic inflammation), normal platelets, renal, and liver function. Faint cardiac murmur noted.

## 2. Audit-Ready Clinical Reasoning Table

| Record ID | Diagnostic Consideration | Supporting Clinical Signals | Missing Information | Risk Level | Safety Constraints & Limitations |
|---|---|---|---|---|---|
| REC-01 | Systemic Lupus Erythematosus (SLE) | Malar rash, symmetrical joint pain, low WBC, mild anemia, elevated ESR/CRP | Anti-dsDNA, ANA titer, complement levels (C3/C4), urinalysis for protein | Moderate–High | Avoid definitive diagnosis; require specialized rheumatologic evaluation |
| REC-02 | Infective Endocarditis / Rheumatic Fever | Low-grade fever, occasional chest pain, faint cardiac murmur, elevated inflammatory markers | Blood cultures (x3 sets), echocardiogram (TTE/TEE), exact murmur characterization | High | Rule out active infection *before* considering immunosuppressive therapy |
| REC-03 | Rheumatoid Arthritis (RA) | Symmetrical joint pain (hands/knees), elevated inflammatory markers | Anti-CCP antibodies, rheumatoid factor (RF), joint imaging (X-rays of hands/wrists) | Moderate | Distinguish erosive joint changes from systemic autoimmune connective tissue disease |

## 3. Zebra Diagnoses (Rare & Clinically Significant Considerations)

**Zebra 1: Adult-Onset Still's Disease (AOSD)**
- Supporting signals: high/spiking or low-grade persistent fever, arthralgia/arthritis, evanescent rash, elevated inflammatory markers, leukocytosis or leukopenia depending on stage
- Missing information: serum ferritin (typically markedly elevated >1,000 ng/mL), negative ANA and rheumatoid factor

**Zebra 2: Systemic Sclerosis (Scleroderma) with Cardiac/Infectious Overlap**
- Supporting signals: multi-organ microvascular involvement, fatigue, musculoskeletal pain, potential cardiac involvement
- Missing information: anticentromere and anti-Scl-70 antibodies, nailfold capillaroscopy, pulmonary function tests, echocardiogram

## 4. Formal Escalation Rules & Uncertainty Framework

- **Specialist consultation triggers:** Immediate referral to Rheumatology on suspicion of connective tissue disease; Cardiology consult for echocardiogram evaluation of the murmur and chest pain
- **Urgent/emergent escalation triggers:** Rapid escalation on high fever, acute shortness of breath, neurological deficits, severe chest pain, or signs of acute cardiac decompensation
- **Mandatory uncertainty statement (enforced in every AI output):**

  > "Note: A definitive diagnosis cannot be established at this time. These findings represent possibilities to be investigated, not confirmed diagnoses. Treatment decisions must be deferred until diagnostic workup is complete and reviewed by an appropriate specialist."

## Why This Matters for AI System Design

This exercise isn't about the AI diagnosing anything — it's the opposite. The value is in the **constraint architecture**: forcing every output into a table that separates "supporting signal" from "missing information," capping risk-level language, and hard-coding an uncertainty disclaimer that cannot be dropped. That's the same pattern needed anywhere an LLM's output could be mistaken for authoritative — legal, financial, medical, or safety-critical automation generally.
