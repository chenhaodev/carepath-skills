# DVT (Deep Vein Thrombosis) - Post-Acute Care Pathway

## Objective
Reduce risk of hospital readmission, ER visits, and premature mortality in patients diagnosed with DVT, either due to evolution/infection of the DVT, development of a PE, or excess anticoagulation therapy. Program targets patients transitioning to home after a hospital stay with a DVT.

## Duration
**30 days** post-discharge

---

## Eligibility Criteria

### Inclusion
- Age 18-75
- Patient with **confirmed diagnosis of DVT on ultrasound**, eligible for outpatient monitoring
- **Stable or improving symptoms**, afebrile, not on any supplemental oxygen
- **No known underlying coagulopathy**
- Ability to complete tasks and questionnaires in-app and use required devices

---

## Primary Outcome Measures

| Outcome | Timeframe | Target |
|---------|-----------|--------|
| **30-Day Hospital Readmission** | 30 days | <10% |
| **30-Day Mortality** | 30 days | <3% |
| **90-Day Mortality** | 90 days | <5% |
| **6-Month Mortality** | 6 months | <8% |
| **Patient Satisfaction** | End of program | >85% satisfaction |

---

## Devices & Monitoring Equipment

See **[Devices Reference](../../shared/devices.md)** for complete specifications.

### Required Devices
- **Pulse Oximeter** (Nonin 3203 - spot check model)
  - **CRITICAL**: Detect PE early (SpO2 drop)
  - Initially Q6hrs, then daily once stable
- **Connected BP Cuff** (Welch Allyn 1700)

---

## Daily Monitoring Protocol & Tasks

### Daily Tasks (Patient-Performed)

1. **Daily Ambulation Plan**
   - **Critical**: Early ambulation prevents clot extension and reduces post-thrombotic syndrome risk
   - Goal: Progressive increase in walking (start 10-15 min, increase to 30 min by week 2)

2. **Medication Adherence Monitoring**
   - **Anticoagulants**: CRITICAL - even short gaps increase thrombotic risk
   - If on warfarin: Track INR appointments
   - If prescribed antibiotics (septic thrombophlebitis): Complete full course

3. **Pulse Oximeter Spot Checks**
   - Initially Q6hrs (first week)
   - Then daily once stable (week 2-4)
   - **Always check if dyspnea develops**

4. **Daily BP Measurements**

### Clinical Team Monitoring

#### Daily DVT Symptom Checker
See **[DVT Questionnaire](../../shared/questionnaires/dvt-questionnaire.md)**
- **PE warning signs**: Dyspnea, chest pain, dizziness (Section A)
- **Affected limb status**: Pain, swelling progression/resolution (Section B)
- **Anticoagulation safety**: Bleeding signs (hematuria, melena, bruising) (Section C)

---

## Alert Thresholds & Escalations

See **[Universal Alert Thresholds](../../shared/alert-thresholds.md)** and **[DVT Comorbidities](../../shared/comorbidity-matrix.md#dvt--chf)**.

### DVT-Specific Post-Acute Alerts (PE CONCERN)

| Parameter | Threshold | PE Risk | Action |
|-----------|-----------|---------|--------|
| **SpO2** | <92% | **HIGH** | **URGENT**: Assess for PE - dyspnea, chest pain, tachycardia → D-dimer, CT PE protocol |
| **Heart Rate** | >100 bpm + dyspnea | High | **Same-day evaluation**: Assess for PE |
| **Sudden Dyspnea** | New/worsening SOB | High | **URGENT**: PE evaluation |
| **Pleuritic Chest Pain** | Pain with breathing | Moderate-High | **Same-day**: Assess for PE |

### Bleeding Alerts (Anticoagulation Safety)

| Finding | Significance | Action |
|---------|--------------|--------|
| **Hematuria** (blood in urine) | Major bleeding concern | **URGENT**: Hold anticoagulation, CBC, urology consult |
| **Melena / Hematochezia** | GI bleeding | **URGENT**: Hold anticoagulation, CBC, GI evaluation |
| **Severe bruising** | Possible over-anticoagulation | Check INR/anti-Xa, hold next dose, reassess |
| **Intracranial bleed symptoms** | Life-threatening | **CALL 911**: Severe headache, confusion, focal weakness |

---

## Complications & Adverse Events to Monitor

### Pulmonary Embolism
- **Signs**: Sudden shortness of breath, chest pain, palpitations, sweating
- **Risk**: Highest in first 4 weeks, ~50% of untreated proximal DVT
- **Action**: **URGENT evaluation** - SpO2, D-dimer, CT PE protocol, anticoagulation continuation

### Thrombophlebitis (Secondary Site Infection)
- **Signs**: Chills/sweats, fever, erythema along vein tract
- **Action**: Blood cultures, IV antibiotics

### Painful Affected Limb (Increased Swelling, Inflammation)
- **Concern**: Clot extension, phlegmasia cerulea dolens (rare but limb-threatening)
- **Action**: Repeat ultrasound, assess anticoagulation adequacy

### Confusion and Worsening Neurological Status
- **Concern**: Intracranial hemorrhage (anticoagulation complication) OR PE with hypoxia
- **Action**: **URGENT evaluation** - head CT if ICH suspected, SpO2 if PE suspected

### Complications of Excess Anticoagulation Therapy
- **Signs**: Bruising, bleeding, dark colored stools
- **Action**: Hold anticoagulation, reversal if major bleeding, adjust doses

---

## Anticoagulation Management

### Duration of Therapy
- **Provoked DVT** (surgery, trauma, immobilization): 3 months
- **Unprovoked DVT**: 3-6 months minimum, consider extended if low bleeding risk
- **Recurrent DVT**: Indefinite anticoagulation
- **Active cancer**: Extended (often 6-12 months or indefinite), prefer LMWH

### Anticoagulant Options

#### Direct Oral Anticoagulants (DOACs) - Preferred
- **Rivaroxaban**: 15mg BID x21 days, then 20mg daily
- **Apixaban**: 10mg BID x7 days, then 5mg BID
- **Advantages**: No monitoring, fixed dose, oral
- **Monitoring**: Renal function periodically

#### Warfarin (with bridging)
- **Target INR**: 2-3
- **Monitoring**: INR every few days initially, then weekly, then monthly once stable
- **Drug interactions**: Extensive (antibiotics, antifungals, many others)
- **Diet**: Consistent vitamin K intake

### Monitoring for Bleeding
- **Daily assessment** via questionnaire
- **CBC**: Baseline and as needed (if bleeding concern - check Hgb drop)
- **Stool guaiac**: If GI symptoms

### Warfarin-Specific: INR Monitoring
- **Week 1-2**: INR every 2-3 days
- **Week 3-4**: INR weekly
- **Month 2+**: INR monthly once stable in range (2-3)
- **Goal**: >70% time in therapeutic range (TTR)

---

## Post-Thrombotic Syndrome Prevention

### Compression Therapy
- **Graduated compression stockings**: 30-40 mmHg
- **Timing**: Start after acute phase resolves (typically week 2-4)
- **Duration**: Daily use for 2 years
- **Benefits**: Reduces PTS risk by ~50%

### Early Mobilization
- **Critical**: Ambulation does NOT increase PE risk (old dogma disproven)
- **Benefits**: Reduces clot burden, improves venous flow, reduces PTS
- **Goal**: 30 min walking daily by week 2

### Leg Elevation
- **When resting**: Elevate affected leg above heart level
- **Benefits**: Reduces swelling, improves venous return

---

## Patient Education Content

### DVT Education Topics (Via Patient App)
- What is DVT? How does it happen?
- **When to contact provider and signs of worsening disease**:
  - **PE signs**: Sudden dyspnea, chest pain, dizziness
  - **Bleeding signs**: Blood in urine/stool, severe bruising
- **Anticoagulation importance**: Even short gaps increase clot risk
- Ambulation benefits (dispel "bed rest" myth)
- Compression stocking use
- When to seek emergency care

---

## Care Coordination & Escalation

### Daily Care Team Monitoring
- Patient questionnaire responses (PE signs, bleeding, adherence)
- Care plan adherence (ambulation, medications, SpO2 checks)
- Alerts and physiologic parameters (SpO2, HR)

### Comorbidity Monitoring and Management
- **DVT + Diabetes**: Monitor glucose
- **DVT + HTN**: Monitor BP
- **DVT + COPD**: Dyspnea assessment challenging (baseline COPD vs PE?)

### Support and Intervention
- **Chat/Video**: Anticoagulation education, PE warning sign education, compression stocking use
- **Escalation**: Same-day clinical calls for PE concern or bleeding

---

## Other Recommended Care

### IV or IM Antibiotic Administration Support (If Prescribed)
- For septic thrombophlebitis (rare)

### IV or IM Anti-coagulation Administration Support (If Prescribed)
- For patients requiring LMWH (enoxaparin) injections

### INR Monitoring (If on Warfarin)
- Home phlebotomy visits OR point-of-care INR testing
- Weekly initially, then monthly once stable

---

## Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **No PE development** | Primary safety goal | Monitor SpO2, symptoms |
| **No major bleeding** | Primary safety goal | Daily bleeding assessment |
| **Anticoagulation adherence** | 100% (critical) | Daily tracking |
| **INR in range** (if warfarin) | >70% time in therapeutic range (TTR) | Weekly/monthly INR checks |
| **Limb symptoms improving** | Pain/swelling decreasing by week 2 | Patient-reported + limb circumference |

---

## References
- Source: Carepath DVT Post-Acute Care Pathway SOP
- ACCP Antithrombotic Guidelines
- Wells Score: DVT clinical prediction rule

**Related Skills**: If patient develops PE or major bleeding, transition to `carepath-acute` skill OR hospital admission for definitive management.
