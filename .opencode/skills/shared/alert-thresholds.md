# Universal Alert Thresholds

This reference document provides standardized vital sign alert thresholds used across all Carepath remote patient monitoring protocols. These thresholds trigger clinical team notifications for immediate review.

## Alert Threshold Table

| Vital Sign | Low Threshold | High Threshold | Units | Clinical Significance |
|------------|---------------|----------------|-------|----------------------|
| **SpO2** | < 92% | — | % | Low oxygen saturation, respiratory distress |
| **Systolic Blood Pressure** | ≤ 90 | ≥ 180 | mmHg | Hypotension or severe hypertension |
| **Diastolic Blood Pressure** | ≤ 50 | ≥ 100 | mmHg | Hypotension or severe hypertension |
| **Respiration Rate** | < 8 | > 24 | breaths/min | Respiratory depression or distress |
| **Heart Rate** | < 55 | > 120 | bpm | Bradycardia or tachycardia |
| **Skin Temperature** | — | > 37.5 | °C | Elevated skin temperature (device-based) |
| **Body Temperature** | — | > 38.5 | °C | High fever (oral/tympanic measurement) |
| **Glucose** | ≤ 2.8 | ≥ 16.7 | mmol/L | Hypoglycemia or severe hyperglycemia |
| **Weight Gain** | — | > 0.9 kg/day OR > 2.3 kg/week | kg | Fluid retention, volume overload |
| **Biovitals Index** | — | > 0.7 | index | Composite risk score from wearable devices |

## Oncology-Specific Alert Thresholds

### Fever in Immunosuppressed Patients

| Parameter | Threshold | Clinical Significance | Action |
|-----------|-----------|----------------------|--------|
| **Temperature (Neutropenic)** | ≥38.0°C (100.4°F) single reading OR ≥37.5°C sustained >1 hour | Febrile neutropenia - medical emergency | **IMMEDIATE ED referral + Notify oncologist + Blood cultures + Antibiotics within 60 min** |
| **Temperature + ANC** | Temp ≥38°C AND ANC <500 | High-risk febrile neutropenia | **Admit to hospital + Empiric broad-spectrum antibiotics** |

**Note**: For cancer patients on active chemotherapy (within 2-4 weeks), use neutropenic fever thresholds even if recent ANC is unknown.

### CTCAE-Based Symptom Severity Alerts

The Common Terminology Criteria for Adverse Events (CTCAE v5.0) provides grading for chemotherapy/radiation toxicity:

| CTCAE Grade | Severity | Functional Impact | Typical Action |
|-------------|----------|-------------------|----------------|
| **Grade 1** | Mild | Asymptomatic or mild symptoms | Patient education, monitor |
| **Grade 2** | Moderate | Minimal intervention indicated, limiting instrumental ADL* | Specialist referral PRN, pharmacologic measures |
| **Grade 3** | Severe | Medically significant, limiting self-care ADL** | Medical intervention, hospitalization often indicated |
| **Grade 4** | Life-threatening | Urgent intervention required | **EMERGENCY - Immediate ED referral** |

*Instrumental ADL: shopping, cooking, managing finances
**Self-care ADL: bathing, dressing, eating

### Oncology Red Flags (Grade 4 Events)

**ANY of the following = IMMEDIATE EMERGENCY**:
- Fever ≥38°C in immunosuppressed patient
- SpO2 ≤94% at rest
- Severe pain (8-10/10) uncontrolled by medication
- New neurological deficits (spinal cord compression suspect)
- Bloody emesis or melena (GI bleeding)
- Suicidal ideation with plan/intent (C-SSRS High Risk)
- No bowel movement >3 days + severe abdominal pain (obstruction)
- Confusion/altered mental status

### Lab-Based Alert Thresholds (Cancer Patients)

| Lab | Critical Low | Critical High | Action |
|-----|--------------|---------------|--------|
| **ANC (Absolute Neutrophil Count)** | <500 cells/µL | - | High infection risk, avoid crowds/sick contacts |
| **Platelets** | <50,000/µL | - | Bleeding risk, avoid NSAIDs, contact sports |
| **Hemoglobin** | <8 g/dL | - | Transfusion consideration |
| **Creatinine** | - | >2x baseline | Nephrotoxic chemo dose adjustment |

**Reference**: See [`../carepath-oncology/SKILL.md`](../carepath-oncology/SKILL.md) for symptom-specific thresholds.

## Disease-Specific Threshold Notes

### Congestive Heart Failure (CHF)
- **Weight gain** is particularly critical: >0.9 kg/day or >2.3 kg/week indicates fluid retention
- **SpO2 <92%** may indicate pulmonary edema
- Monitor closely for combined weight + SpO2 alerts

### COPD & Pneumonia
- **SpO2 <92%** is primary respiratory distress indicator
- **Respiration Rate >24** suggests exacerbation
- Baseline SpO2 may be lower than general population; use patient-specific targets

### Hypertension
- **Systolic BP ≥180** or **Diastolic BP ≥100** indicates hypertensive urgency
- **Systolic BP ≤90** indicates possible medication over-treatment

### Diabetes
- **Glucose ≤2.8 mmol/L** requires immediate hypoglycemia protocol
- **Glucose ≥16.7 mmol/L** with symptoms may indicate DKA/HHS
- Monitor trends, not just single values

### DVT (Deep Vein Thrombosis)
- **SpO2 <92%** may indicate pulmonary embolism (PE)
- **Heart Rate >120** may accompany PE
- Combined respiratory distress + tachycardia requires urgent evaluation

### COVID-19
- **SpO2 <92%** is critical threshold for escalation
- **Temperature >38.5°C** indicates persistent/worsening infection
- Monitor for "silent hypoxemia" (low SpO2 without dyspnea)

## Usage Guidelines

1. **Threshold Triggers**: Alerts are generated when any vital sign crosses the specified threshold
2. **Clinical Context**: Always interpret alerts within patient's clinical context and baseline values
3. **Escalation**: These thresholds indicate need for clinical review; escalation protocols are defined by care teams
4. **Device Reliability**: Ensure proper device placement and patient compliance before responding to alerts
5. **Trend Analysis**: Single threshold violations may be artifact; confirm with repeat measurements and trend review

## References

- Source: Carepath Standard Operating Procedures (SOPs)
- Based on evidence-based clinical guidelines for remote patient monitoring
- Updated: 2025

---

**Note**: These thresholds provide alerts for clinical review. They do not replace clinical judgment or patient-specific care plans. Care teams should define their own escalation protocols based on organizational resources and patient acuity.
