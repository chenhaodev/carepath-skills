# Pneumonia - Post-Acute Care Pathway

## Objective
Reduce risk of hospital readmission, ER visits, and premature mortality in pneumonia patients while optimizing recovery. Program targets patients diagnosed and admitted for pneumonia, now transitioning to home.

## Duration
**30 days** post-discharge

---

## Eligibility Criteria

### Inclusion
- Age 18-75
- Patient with confirmed diagnosis of **Pneumonia**, eligible for outpatient monitoring
- **Stable or improving symptoms**
- Maintains **SpO2 ≥92% on no more than 4L nasal cannula**, OR requires less than 6 hrs O2 per day
- Ability to complete tasks and questionnaires in-app and use required devices

---

## Primary Outcome Measures

| Outcome | Timeframe | Target |
|---------|-----------|--------|
| **30-Day Hospital Readmission** | 30 days | <15% |
| **30-Day Mortality** | 30 days | <5% |
| **90-Day Mortality** | 90 days | <8% |
| **Patient Satisfaction** | End of program | >85% satisfaction |

---

## Devices & Monitoring Equipment

See **[Devices Reference](../../shared/devices.md)** for complete specifications.

### Required Devices
- **Everion Armband**
  - Continuous HR, RR, SpO2, skin temperature, activity levels
  - Detects persistent hypoxemia or fever
- **Thermometer**
  - Essential for fever monitoring during antibiotic course

---

## Daily Monitoring Protocol & Tasks

### Daily Tasks (Patient-Performed)

1. **Twice Daily Temperature Monitoring (Week 1)**
   - Morning and evening
   - **Critical**: Should be afebrile by day 3-5 of antibiotics
   - Continue if fevers persist beyond week 1

2. **Medication Adherence** (If Prescribed Antibiotics)
   - Complete full antibiotic course (typically 5-7 days, sometimes 10-14 days)
   - Record doses taken
   - **Barrier assessment**: Cost, side effects, forgetting - address immediately

### Clinical Team Monitoring

#### Daily Pneumonia Symptom Checker
See **[Pneumonia Questionnaire](../../shared/questionnaires/pneumonia-questionnaire.md)**
- Antibiotic adherence (did you fill prescription? taking as prescribed?)
- Overall improvement ("feeling better?")
- Cough and sputum assessment (increasing, decreasing, color)
- Dyspnea changes
- Activity tolerance

---

## Alert Thresholds & Escalations

See **[Universal Alert Thresholds](../../shared/alert-thresholds.md)** and **[Pneumonia Comorbidities](../../shared/comorbidity-matrix.md#pneumonia--copd)**.

### Pneumonia-Specific Post-Acute Alerts

| Parameter | Threshold | Action |
|-----------|-----------|--------|
| **Temperature** | >38.5°C after day 5 of antibiotics | **Same-day evaluation**: Treatment failure, imaging, culture, change antibiotics |
| **SpO2** | <92% | **Urgent**: Assess for complications (effusion, ARDS, PE), consider readmission |
| **Worsening Dyspnea** | After initial improvement | **Urgent**: Chest X-ray for complications (effusion, empyema, abscess) |
| **Brown Sputum** | New onset | **Urgent evaluation**: Hemorrhage, necrotizing pneumonia, PE |
| **Chest Pain** | Pleuritic (worse with breathing) | **Same-day**: Assess for parapneumonic effusion or PE |

---

## Complications & Adverse Events to Monitor

### Shortness of Breath, Respiratory Distress
- **Concern**: Incomplete resolution, complications (effusion, PE, ARDS)
- **Action**: SpO2 monitoring, chest X-ray, consider hospital readmission

### Worsening Cough with Changing Mucus/Phlegm and High-Grade Fever
- **Concern**: Treatment failure, resistant organism, lung abscess
- **Action**: Sputum culture, chest X-ray/CT, broaden antibiotic coverage

### Confusion and Worsening Neurological Status
- **Concern**: Hypoxemia, sepsis, meningoencephalitis (rare)
- **Action**: **Urgent evaluation** - SpO2, mental status exam, consider hospital readmission

### Vomiting and Diarrhea
- **Concern**: Antibiotic side effects (common), dehydration
- **Action**: Assess hydration, consider antibiotic change if severe, anti-nausea medication

### Chest Pain
- **Concern**: Parapneumonic effusion, pulmonary embolism, pleuritis
- **Action**: Chest X-ray, D-dimer if PE suspected, pain management

---

## Pneumonia Recovery Management

### Antibiotic Completion
- **Duration**: Typically 5-7 days (may extend to 10-14 days for severe CAP)
- **Adherence Critical**: Early discontinuation increases treatment failure and resistance risk
- **Side Effects**: GI upset (nausea, diarrhea) most common - manage symptomatically

### Oxygen Therapy (If Needed)
- **Indication**: SpO2 <92% at rest or with exertion
- **Goal**: Wean O2 as pneumonia resolves (typically off O2 by week 2-3)
- **Monitoring**: Daily SpO2 checks, especially with activity

### Activity Progression
- **Week 1**: Rest predominates, gradual increase in ADLs
- **Week 2-3**: Progressive ambulation, light activity
- **Week 4**: Most patients return to baseline activity
- **Concern**: Persistent fatigue common (may last 4-6 weeks)

### Follow-Up Imaging
- **Indication**: High-risk patients (age >65, smokers, concerning initial findings)
- **Timing**: Chest X-ray at 6 weeks post-treatment
- **Purpose**: Ensure infiltrate resolution, rule out underlying lesion (malignancy)

---

## Patient Education Content

### Pneumonia Education Topics (Via Patient App)
- **Timeline and progression of disease**:
  - Day 1-3: May feel worse before better
  - Day 3-5: Should start improving
  - Week 2-4: Most symptoms resolved
  - Fatigue may persist 4-6 weeks
- **When to contact provider and signs of worsening disease**:
  - Persistent fever >5 days
  - Worsening dyspnea
  - New chest pain
  - Confusion
  - Hemoptysis (coughing blood)
- **Antibiotic importance**: Complete full course, don't stop when feeling better
- **Rest and nutrition**: Adequate sleep, protein intake for immune recovery
- **Hydration**: 2-3L fluid daily (helps thin secretions)

---

## Care Coordination & Escalation

### Daily Care Team Monitoring
- Patient questionnaire responses (improvement trajectory, cough, dyspnea)
- Alerts and physiologic parameters (SpO2, temperature, RR)

### Comorbidity Monitoring and Management
- **Pneumonia + Diabetes**: Infection worsens glucose control - coordinate with diabetes management
- **Pneumonia + HTN**: Monitor BP
- **Pneumonia + COPD**: Differentiate pneumonia from COPD exacerbation, may coexist

### Support and Intervention
- **Chat/Video**: Antibiotic adherence, symptom assessment, recovery timeline expectations
- **Escalation**: Same-day clinical calls for persistent fever, worsening symptoms

### Transition Back to Acute Care
**Criteria for Re-escalation**: See **[Transition from Post-Acute](./transition-from-acute.md)**
- Persistent fever >5 days despite antibiotics
- Worsening hypoxemia (SpO2 <92% on supplemental O2)
- New complications (effusion, empyema, abscess)
- Sepsis signs (hypotension, confusion)
- **Action**: Transition to `carepath-acute` skill OR hospital admission for complications

---

## Other Recommended Care

### IV or IM Antibiotic Administration Support (If Prescribed)
- Home health RN visits for ceftriaxone or other parenteral antibiotics
- Typically daily x 3-5 days, then transition to oral

### Labs
- **CBC**: If prescribed (assess WBC trend)
- Follow-up labs typically not needed if recovering well

### Follow-Up Chest X-Ray (If Prescribed)
- **High-risk patients**: Age >65, smokers, initial severe findings
- **Timing**: 6 weeks post-treatment
- **Purpose**: Document infiltrate resolution, rule out post-obstructive pneumonia (mass)

---

## Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **No 30-day readmission** | Primary goal | Track hospital admissions |
| **Afebrile by day 5** | Clinical resolution | Temperature trend |
| **Antibiotic course completion** | 100% | Adherence tracking |
| **SpO2 normalization** | >92% on room air by week 2-3 | Daily SpO2 monitoring |
| **Return to baseline activity** | By week 4 | Patient-reported functional status |

---

## References
- Source: Carepath Pneumonia Post-Acute Care Pathway SOP
- IDSA/ATS Community-Acquired Pneumonia Guidelines 2019
- Expected Treatment Response Timeline: Mandell LA, et al. Clin Infect Dis 2007

**Related Skills**: If patient deteriorates, transition back to `carepath-acute` skill for intensive hospital-at-home management or hospital admission for complications.
