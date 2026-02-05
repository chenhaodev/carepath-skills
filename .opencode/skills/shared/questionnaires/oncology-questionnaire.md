# Oncology Symptom Questionnaire

### Purpose
Daily symptom monitoring for cancer patients undergoing active treatment (chemotherapy, immunotherapy, radiation) or in post-treatment recovery. This tool integrates NCCS Distress Thermometer, CTCAE-based symptom grading, and emergency red flag screening.

### Administration Frequency
- **High Risk** (Active chemo/neutropenic): Daily
- **Moderate Risk**: Every 2-3 days
- **Low Risk**: Weekly

---

## Section A: EMERGENCY RED FLAGS

**Question 1: Do you have ANY of these critical symptoms?**

**If YES to ANY of the following, notify clinical team IMMEDIATELY or Go to Emergency Department:**

- ☐ **Fever ≥38°C** (especially if on chemotherapy)
- ☐ **Difficulty breathing** or feeling like you can't catch your breath
- ☐ **Chest pain** or coughing up blood
- ☐ **Severe pain** (8-10/10) not controlled by medication
- ☐ **Unable to eat or drink** for more than 24 hours
- ☐ **Bloody vomit or stool** (black, tarry, or red)
- ☐ **New weakness** in arms or legs
- ☐ **Confusion** or difficulty staying awake
- ☐ **Thoughts of harming yourself**
- ☐ **New swelling with pain** in one leg (DVT concern)
- ☐ **Severe rash** covering >30% of body
- ☐ **No bowel movement for 3+ days** with severe abdominal pain

**Action**: ANY checked → Immediate clinical contact or Emergency Department

---

## Section B: Daily Symptom Assessment

Please rate your symptoms today using the scale below (0 = None, 10 = Worst possible).

| Symptom Category | Today's Status | Severity (0-10) |
|------------------|----------------|-----------------|
| **Pain** | None / Mild / Moderate / Severe | [0-10] |
| **Nausea** | None / Mild / Moderate / Severe | |
| **Fatigue** | None / Mild / Moderate / Severe | |
| **Shortness of Breath** | None / At rest / With activity | |
| **Constipation** | Last BM: _____ days ago | |
| **Diarrhea** | # stools today: _____ | |
| **Mouth Sores** | None / Mild / Painful | |
| **Skin Problems** | None / Rash / Hand-foot syndrome | |
| **Numbness/Tingling** | None / Fingers/Toes / Limiting function | |
| **Sleep Quality** | Good / Fair / Poor | Hours: ____ |

---

## Section C: Psychosocial Screening

### 1. Distress Thermometer
*How distressed have you been during the past week?*

```
0 (No distress) ━━━━━━━━━━ 10 (Extreme distress)
```
**Score**: ______
*Score ≥4 indicates moderate-severe distress requiring further assessment.*

### 2. Mood Screening (PHQ-2)
Over the last 2 weeks, how often have you been bothered by the following problems?

1. **Little interest or pleasure in doing things?**
   - ☐ Yes
   - ☐ No

2. **Feeling down, depressed, or hopeless?**
   - ☐ Yes
   - ☐ No

**Action**: If YES to either question → Administer full PHQ-9 screening.

---

## Clinical Interpretation

### Section A: Emergency Red Flags
- **Fever + Chemotherapy**: High suspicion for **Febrile Neutropenia**. Requires immediate CBC and empiric antibiotics. See `../carepath-oncology/references/symptom-febrile-neutropenia.md`.
- **Chest Pain + Dyspnea**: Rule out **Pulmonary Embolism** (cancer is hypercoagulable state), pneumonia, or malignant pleural effusion. See `symptom-dyspnea.md`.
- **Suicidal Ideation**: Immediate safety assessment required. Initiate C-SSRS protocol. See `symptom-distress.md`.
- **New Leg Swelling**: Suspicion for **DVT**. See `symptom-dvt.md`.
- **Severe Rash**: Rule out Stevens-Johnson Syndrome (SJS) or severe drug reaction.

### Section B: Symptom Severity Mapping (CTCAE v5.0)

| Symptom | Grade 1 (Mild) | Grade 2 (Moderate) | Grade 3 (Severe) | Action |
|---------|----------------|--------------------|------------------|--------|
| **Pain** | 1-3/10 | 4-6/10, limits instrumental ADL | 7-10/10, limits self-care ADL | Grade 3 → Urgent escalation |
| **Diarrhea** | <4 stools > baseline | 4-6 stools > baseline | ≥7 stools > baseline, incontinence | Grade 3 → Hospitalization/IV fluids |
| **Nausea** | Loss of appetite | Decreased oral intake | Inadequate intake, tube feeding indicated | Grade 3 → IV antiemetics |
| **Neuropathy** | Asymptomatic/Mild | Moderate, limits instrumental ADL | Severe, limits self-care ADL | Grade 2-3 → Dose modification |
| **Fatigue** | Relieved by rest | Not relieved by rest, limits instrumental ADL | Limits self-care ADL | Grade 3 → Rule out anemia/metabolic causes |

### Section C: Psychosocial
- **Distress Score ≥4**: Trigger referral to social work, psychology, or nurse navigator.
- **PHQ-2 Positive**: Proceed to PHQ-9. If PHQ-9 ≥10, consider depression treatment/referral.

---

## Risk Stratification

**High-Risk Patients** (Daily monitoring):
- Active chemotherapy (received within last 14 days)
- Known neutropenia (ANC <1000)
- High symptom burden (≥3 symptoms rated >4/10)
- Recent hospitalization (<30 days)
- Multiple comorbidities (see `../shared/comorbidity-matrix.md`)

**Moderate-Risk Patients** (Monitor every 2-3 days):
- Stable on maintenance therapy (immunotherapy, hormonal)
- Radiation therapy (active)
- Post-surgical recovery (weeks 2-6)

**Low-Risk Patients** (Weekly monitoring):
- Long-term survivorship
- Hormonal therapy only (stable)

---

## Treatment Considerations

### Monitoring Intensity Matrix

| Risk Level | Questionnaire Frequency | Clinical Review Frequency | Alert Thresholds |
|------------|-------------------------|---------------------------|------------------|
| **High Risk** | Daily | Every 2-3 days | Lower threshold (Grade 2 symptoms) |
| **Moderate Risk** | Every 2-3 days | Weekly | Standard threshold (Grade 3 symptoms) |
| **Low Risk** | Weekly | As needed | High threshold (Emergency signs) |

---

## Correlation with Objective Data

**Key Labs & Vitals to Cross-Reference**:

- **Temperature**: Fever threshold ≥38.0°C (single reading) or ≥38.3°C. Critical in neutropenic patients.
- **SpO2**: <94% correlates with Grade 3 Dyspnea or potential PE/Pneumonia.
- **Weight**:
  - Loss >5% in 1 month = Malnutrition risk (Cachexia).
  - Gain >2kg in 2-3 days = Fluid retention (CHF/Renal toxicity).
- **CBC (Complete Blood Count)**:
  - **ANC <500**: Severe neutropenia (High infection risk).
  - **Platelets <50k**: Bleeding risk (Avoid NSAIDs, fall precautions).
  - **Hemoglobin <8.0**: Symptomatic anemia (Fatigue, Dyspnea).
- **Electrolytes**: Monitor for imbalances due to vomiting/diarrhea (Hypokalemia, Hyponatremia).

---

## Documentation Template

```
Oncology Symptom Check - Day [X]

RED FLAGS: [None / ***SEE EMERGENCY SECTION***]

Daily Symptoms:
- Pain: [Score/10], Location: [___], Controlled: [Y/N]
- GI: Nausea [Grade], BM [frequency]
- Energy: Fatigue [Grade], Activity Level: [___]
- Respiratory: SOB [at rest/activity], SpO2: [___]
- Neuro: CIPN [Grade], Falls: [Y/N]

Psychosocial:
- Distress Thermometer: [Score/10]
- Mood: [PHQ-2 positive/negative]

Assessment:
- Overall Status: [Stable/Worsening/Improving]
- CTCAE Highest Grade: [___]

Plan:
- [Action items]
- Next Review: [Date]
```

---

## References

- **NCCN Guidelines for Supportive Care**: Distress Management, Adult Cancer Pain, Antiemesis.
- **CTCAE v5.0**: Common Terminology Criteria for Adverse Events, US National Cancer Institute.
- **Singapore Cancer Network Clinical Pathway Guide**.
- **PHQ-2/PHQ-9**: Kroenke K, et al. Med Care. 2003.
- **Distress Thermometer**: NCCN Clinical Practice Guidelines in Oncology.

---

**Clinical Note**: This questionnaire is a screening tool. All Grade 3-4 toxicities and Emergency Red Flags require immediate clinical evaluation. Symptom management should follow specific pathway protocols (e.g., `symptom-pain.md`, `symptom-nausea.md`).
