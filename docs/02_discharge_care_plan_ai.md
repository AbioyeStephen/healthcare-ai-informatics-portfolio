# Patient-Friendly Discharge Care Plan Workflow

> **⚠️ Synthetic case:** The patient case below (including the name used) is a fictional training exercise scenario. No real patient data is used.

## 1. Clinical Parameters & Constraints Integration

**Case:** Laparoscopic cholecystectomy discharge, Day 1 post-op, cleared for next-day discharge.

- **Comorbidities & medications:** Type 2 Diabetes (Metformin 500 mg BID), Hypertension (Lisinopril 10 mg daily), Reflux (Omeprazole 20 mg daily)
- **Allergies:** Penicillin (hives and throat swelling — strictly documented, must be flagged in every output)
- **Wound care:** 4 laparoscopic incision sites with Steri-strips; keep dry for 48 hours; gentle pat dry after showers
- **Activity & diet:** No lifting >10 lbs for 2 weeks; light walking from Day 2; no driving for 1 week or while on pain meds. Clear liquids Day 1, low-fat soft diet Days 2–5, light balanced meals thereafter; avoid fried/greasy/spicy foods
- **Social context & health literacy:** Reads at 6th–7th grade level; prefers numbered instructions; lives alone from Day 4 onward (family member assists Days 1–3)

## 2. Patient-Facing Prompt Engineering Framework

The core engineering problem here: an LLM asked to "simplify" clinical instructions will often silently drop safety-critical detail in the name of readability. The prompt below forces every constraint to survive translation, regardless of reading-level simplification.

```text
You are an expert clinical informatics nurse creating a patient-friendly discharge care plan.

Target Audience: A 67-year-old patient reading at a 6th-7th grade level who prefers
numbered instructions.

Constraints — every item below MUST appear in the output, in plain language:
1. Medications: Metformin 500mg twice daily with meals, Lisinopril 10mg daily,
   Omeprazole 20mg daily before breakfast, Acetaminophen 500mg every 6 hours PRN pain
   (max 4 doses/day). Highlight Penicillin allergy warning explicitly.
2. Wound Care: Keep incisions dry for 48 hours; pat dry gently thereafter.
3. Activity: No lifting over 10 lbs for 2 weeks; no driving for 1 week.
4. Diet: Low-fat soft diet for days 2-5; avoid greasy/fried foods.
5. Red Flags (Return to ER): Fever > 101°F, worsening abdominal pain, jaundice,
   pus/redness at incision sites, inability to keep fluids down.
6. Support: Note family assistance for the first 3 days and independent living
   from Day 4.

Format with clear numbering, empathetic tone, and zero medical jargon.
```

## Why This Matters for AI System Design

This is a template for a broader pattern: **constraint-locked generation.** Instead of trusting the model to remember every safety detail across a "make this simpler" instruction, the prompt enumerates every non-negotiable fact up front and makes simplification the only free variable. The same architecture applies anywhere AI-generated content needs to stay both accessible *and* provably complete — compliance summaries, onboarding documentation, or customer-facing policy explanations.
