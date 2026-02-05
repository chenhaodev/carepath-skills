---
name: carepath-oncology
description: |
  Clinical decision support for oncology symptom management across 18 common pathways (Fever, Pain, Nausea, etc.) using CTCAE grading.

  **Triggers**: "oncology", "cancer", "chemotherapy", "neutropenia", "CTCAE", "toxicity", "chemo side effects", "cancer treatment", "febrile neutropenia"

  Provides protocol guidance for cancer symptom management including grading, assessment, alert escalation, and home care interventions.
---

# Carepath Oncology Symptom Pathways

**Version**: 1.0  
**Optimized for**: Qwen-Pro API + OpenCode  
**Coverage**: 18 oncology symptom pathways

---

## Quick Reference: Symptom Selection

Use this table to quickly identify which symptom pathway to reference based on patient presentation:

| Symptom | CTCAE Grade | Urgency | Key Assessment Tool | Critical Alert |
|---------|-------------|---------|---------------------|----------------|
| **[Febrile Neutropenia/Fever](references/symptom-fever.md)** | Grade 3-4 | Critical | Thermometer | Temp >38.3°C (101°F) or >38.0°C for 1h |
| **[Nausea & Vomiting](references/symptom-nausea.md)** | Grade 1-3 | Urgent | MASCC Antiemesis Tool | Vomiting >6x/24h or dehydration signs |
| **[Pain](references/symptom-pain.md)** | Grade 1-3 | Urgent | 0-10 Scale / OPQRST | Pain score >7/10 or new severe pain |
| **[Dyspnea](references/symptom-dyspnea.md)** | Grade 1-4 | Critical | Pulse Ox, RR | SpO2 <90%, RR >24, air hunger |
| **[Constipation](references/symptom-constipation.md)** | Grade 1-3 | Advisory | Bowel Diary | No BM >3 days, severe abdominal pain |
| **[Diarrhea](references/symptom-diarrhea.md)** | Grade 1-3 | Urgent | Stool Count | >7 stools/day over baseline, bloody stool |
| **[Mucositis](references/symptom-mucositis.md)** | Grade 1-3 | Urgent | WHO Oral Toxicity Scale | Unable to swallow liquids/meds |
| **[Fatigue](references/symptom-fatigue.md)** | Grade 1-3 | Advisory | 0-10 Scale | Unable to perform ADLs, sudden onset |
| **[Peripheral Neuropathy (CIPN)](references/symptom-neuropathy.md)** | Grade 1-3 | Advisory | TNS-c | Falls, unable to hold objects |
| **[Distress](references/symptom-distress.md)** | Grade 1-3 | Urgent | Distress Thermometer | Suicidal ideation, panic attack |
| **[Sleep Problems](references/symptom-sleep.md)** | Grade 1-2 | Advisory | PSQI | <4h sleep/night, safety risk |
| **[Lymphedema](references/symptom-lymphedema.md)** | Grade 1-3 | Advisory | Limb Circumference | Acute swelling, redness/heat (infection) |
| **[Skin Problems](references/symptom-skin.md)** | Grade 1-3 | Urgent | BSA % | Rash >50% BSA, blistering, peeling |
| **[Anorexia/Cachexia](references/symptom-anorexia.md)** | Grade 1-3 | Advisory | Weight, Intake % | Weight loss >10% baseline, no intake >24h |
| **[Hot Flashes](references/symptom-hotflashes.md)** | Grade 1-2 | Advisory | Frequency/Severity | Impacting sleep/ADLs significantly |
| **[Memory/Concentration](references/symptom-memory.md)** | Grade 1-2 | Advisory | FACT-Cog | Safety concerns, sudden confusion |
| **[Sexual Problems](references/symptom-sexual.md)** | Grade 1-2 | Advisory | PROMIS-Sexual | Pain, distress impacting relationship |
| **[Spiritual Concerns](references/symptom-spiritual.md)** | N/A | Advisory | FICA Tool | Existential distress, hopelessness |

---

## When to Use This Skill

### Oncology Symptom Management Criteria

**Use `carepath-oncology` skill when patient**:

1. **Is undergoing active cancer treatment**:
   - Chemotherapy
   - Immunotherapy
   - Radiation therapy
   - Targeted therapy

2. **Reports new or worsening symptoms**:
   - Treatment-related toxicities (CTCAE)
   - Disease-related symptoms
   - Post-surgical complications

3. **Requires home-based symptom management**:
   - Grading severity (Is this mild or dangerous?)
   - Self-care instructions
   - Triage decision support (Stay home vs. Clinic vs. ER)

**Do NOT use for**:
- Routine cancer screening protocols
- Staging or diagnostic interpretation
- Chemotherapy regimen selection (oncologist purview)
- End-of-life/Hospice specific protocols (unless symptom management overlaps)

---

## How to Use This Skill

### Step 1: Identify Symptom Pathway

Match patient's primary complaint to one of 18 pathways using the Quick Reference table.

**For patients with multiple symptoms**:
- Address the **MOST URGENT** symptom first (e.g., Fever > Nausea).
- Use the NOPQRSTUV framework for assessment.

### Step 2: Assess & Grade (CTCAE)

Open symptom-specific reference and determine severity:
- **Grade 1 (Mild)**: Asymptomatic or mild symptoms; clinical or diagnostic observations only; intervention not indicated.
- **Grade 2 (Moderate)**: Minimal, local or noninvasive intervention indicated; limiting age-appropriate instrumental ADL.
- **Grade 3 (Severe)**: Severe or medically significant but not immediately life-threatening; hospitalization or prolongation of hospitalization indicated; disabling; limiting self care ADL.
- **Grade 4 (Life-threatening)**: Urgent intervention indicated.

### Step 3: Protocol Implementation

Each symptom pathway reference provides:

1. **Assessment Questions**: NOPQRSTUV framework.
2. **Grading Criteria**: CTCAE v5.0 definitions.
3. **Triage/Escalation**: Red flags for ER/Clinic.
4. **Pharmacologic Interventions**: Standard meds (e.g., Zofran for nausea).
5. **Non-Pharmacologic Interventions**: Diet, lifestyle, comfort measures.
6. **Patient Education**: What to teach the patient/caregiver.

### Step 4: Alert Management

**Universal alert thresholds** are documented in [`shared/alert-thresholds.md`](../shared/alert-thresholds.md).

**Escalation levels**:
- 🔴 **CRITICAL (Red)**: Immediate ER/911 (e.g., Febrile Neutropenia, Spinal Cord Compression).
- 🟠 **URGENT (Orange)**: Call Oncology Clinic/Provider within 1 hour (e.g., Uncontrolled vomiting).
- 🟡 **ADVISORY (Yellow)**: Monitor/Symptom Management at home (e.g., Grade 1 rash).

### Step 5: Questionnaires

Daily patient-reported symptom questionnaires are in [`shared/questionnaires/`](../shared/questionnaires/):

- [`oncology-questionnaire.md`](../shared/questionnaires/oncology-questionnaire.md) - General symptom surveillance (ESAS-r based).

---

## Symptom Pathway References

### 1. Febrile Neutropenia / Fever
**File**: [`references/symptom-fever.md`](references/symptom-fever.md)
**Critical**: Oncologic Emergency. Requires immediate antibiotics.

### 2. Nausea & Vomiting
**File**: [`references/symptom-nausea.md`](references/symptom-nausea.md)
**Focus**: Prevention of dehydration, electrolyte imbalance.

### 3. Pain
**File**: [`references/symptom-pain.md`](references/symptom-pain.md)
**Focus**: Comprehensive assessment, opioid/non-opioid management.

### 4. Dyspnea (Breathing Problems)
**File**: [`references/symptom-dyspnea.md`](references/symptom-dyspnea.md)
**Focus**: Rule out PE, pneumonia, effusion.

### 5. Constipation
**File**: [`references/symptom-constipation.md`](references/symptom-constipation.md)
**Focus**: Opioid-induced constipation management.

### 6. Diarrhea
**File**: [`references/symptom-diarrhea.md`](references/symptom-diarrhea.md)
**Focus**: Immunotherapy-induced colitis vs. chemo-induced.

### 7. Mucositis (Mouth/Swallowing)
**File**: [`references/symptom-mucositis.md`](references/symptom-mucositis.md)
**Focus**: Oral care, pain control, nutrition.

### 8. Fatigue
**File**: [`references/symptom-fatigue.md`](references/symptom-fatigue.md)
**Focus**: Energy conservation, rule out anemia/thyroid issues.

### 9. Peripheral Neuropathy (CIPN)
**File**: [`references/symptom-neuropathy.md`](references/symptom-neuropathy.md)
**Focus**: Safety/Falls prevention, symptom relief.

### 10. Distress (Anxiety/Depression)
**File**: [`references/symptom-distress.md`](references/symptom-distress.md)
**Focus**: Anxiety, depression, coping.

### 11. Sleep Problems
**File**: [`references/symptom-sleep.md`](references/symptom-sleep.md)
**Focus**: Sleep hygiene, steroid-induced insomnia.

### 12. Lymphedema (Abnormal Swelling)
**File**: [`references/symptom-lymphedema.md`](references/symptom-lymphedema.md)
**Focus**: Early detection, compression, skin care.

### 13. Skin Problems (Rash, Hand-Foot Syndrome)
**File**: [`references/symptom-skin.md`](references/symptom-skin.md)
**Focus**: EGFR rash, Hand-Foot syndrome, radiation dermatitis.

### 14. Anorexia/Cachexia (Appetite)
**File**: [`references/symptom-anorexia.md`](references/symptom-anorexia.md)
**Focus**: Nutritional support, small frequent meals.

### 15. Hot Flashes
**File**: [`references/symptom-hotflashes.md`](references/symptom-hotflashes.md)
**Focus**: Hormonal therapy side effects.

### 16. Memory/Concentration
**File**: [`references/symptom-memory.md`](references/symptom-memory.md)
**Focus**: "Chemo brain" strategies.

### 17. Sexual Problems
**File**: [`references/symptom-sexual.md`](references/symptom-sexual.md)
**Focus**: Vaginal dryness, ED, libido.

### 18. Spiritual Concerns
**File**: [`references/symptom-spiritual.md`](references/symptom-spiritual.md)
**Focus**: Meaning, hope, connection.

---

## Cancer-Type Specific Treatment Pathways

### RET Fusion-Positive Lung Cancer
**File**: [`references/treatment-ret-positive-lung-cancer.md`](references/treatment-ret-positive-lung-cancer.md)
**Focus**: First-line targeted therapy (Selpercatinib/Pralsetinib), monitoring, adverse event management.

---

## Shared Resources

All oncology pathways reference these shared knowledge bases:

### 1. Alert Thresholds & Escalation Protocols
**File**: [`shared/alert-thresholds.md`](../shared/alert-thresholds.md)

### 2. Monitoring Devices Catalog
**File**: [`shared/devices.md`](../shared/devices.md)

### 3. Nurse Response Protocols
**File**: [`shared/nurse-response-protocols.md`](../shared/nurse-response-protocols.md)

### 4. Comorbidity Interaction Matrix
**File**: [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md)

---

## Clinical Pearls

### Universal Oncology Principles

1. **Fever is a Medical Emergency**: In chemotherapy patients, fever >38.3°C (101°F) is febrile neutropenia until proven otherwise. Immediate ER evaluation required.

2. **Grading Matters**: Interventions are tied to CTCAE grades. Grade 1 = Home care. Grade 3+ = Hospital/Clinic.

3. **NOPQRSTUV Assessment**:
   - **N**umber (How many symptoms?)
   - **O**nset
   - **P**rovokes/Palliates
   - **Q**uality
   - **R**adiation
   - **S**everity
   - **T**iming
   - **U**nderstanding (Patient's view)
   - **V**alues (Goals of care)

4. **Immunotherapy Red Flags**: Diarrhea (Colitis), SOB (Pneumonitis), Rash (Dermatitis) in patients on Checkpoint Inhibitors require early steroid intervention, not just symptom management.

---

## Updates & Maintenance

**Current Version**: 1.0  
**Last Updated**: 2026-02-05  
**Next Review**: Quarterly

**Changelog**:
- 2026-02-05: Initial release with 18 symptom pathways

---

## References

**Primary Source Document**: Singapore Cancer Network Clinical Pathway Guide

**Clinical Guidelines**:
- NCCN Guidelines for Supportive Care
- ASCO Clinical Practice Guidelines
- ONS (Oncology Nursing Society) Putting Evidence Into Practice (PEP)
- CTCAE v5.0 (Common Terminology Criteria for Adverse Events)
- MASCC Guidelines
