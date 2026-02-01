# DVT (Deep Vein Thrombosis) - Acute Care Pathway

## Objective
Enable physiologic monitoring and geographically-distributed care coordination of patients with DVT who are starting anticoagulation treatment in a hospital-at-home setting.

## Duration
**2-5 days** (typical 3-4 days)

---

## Eligibility Criteria

### Inclusion
- **Confirmed DVT** requiring admission for:
  - Anticoagulation initiation, OR
  - Anticoagulation management, OR
  - Bridging therapy (heparin → warfarin/DOAC)

### Exclusion Criteria
- **Hemodynamically unstable** (hypotensive)
- **O2 requirement >4L nasal cannula** to maintain SpO2 >90% (suggests massive PE)
- **Requiring IV pain medication** (severe uncontrolled pain)

---

## Primary Outcome Measures

| Outcome | Timeframe | Target |
|---------|-----------|--------|
| **30-Day ED Presentation** | 30 days | Minimize VTE-related ED visits |
| **30-Day Readmission** | 30 days | <10% |
| **30-Day Mortality** | 30 days | <3% |
| **Patient Satisfaction** | End of program | >85% satisfaction |

---

## Devices & Monitoring Equipment

See **[Devices Reference](../../shared/devices.md)** for complete specifications.

### Required Devices
- **Connected BP Cuff** (Welch Allyn 1700 OR Omron BP7000)
  - Monitor for hypotension (PE) or hypertension
- **Connected Pulse Oximeter** (Nonin 3230)
  - **Critical**: Detect PE early (SpO2 drop)

### Optional Devices (based on severity and clinician preference)
- **Continuous Telemetry** (VitalConnect VitalPatch)*
  - For higher-risk patients or those with respiratory symptoms
  - Monitors HR (tachycardia suggests PE), RR, SpO2, arrhythmia detection
- **Oral Thermometer*
  - Monitor for fever (septic thrombophlebitis)

---

## Daily Monitoring Protocol

### Clinical Team Reviews (Daily)
1. **Physiologic Data Review**
   - **SpO2**: Most critical PE indicator - any drop requires urgent evaluation
   - **Heart rate**: Tachycardia (>100) suggests PE or anxiety
   - **Respiratory rate**: Tachypnea suggests PE
   - **BP**: Hypotension suggests massive PE
   - **Temperature**: Fever suggests septic thrombophlebitis

2. **Subjective Patient Data Review**
   - **Daily DVT Symptom Checker**: See **[DVT Questionnaire](../../shared/questionnaires/dvt-questionnaire.md)**
     - **PE warning signs**: Dyspnea, chest pain, dizziness
     - **Affected limb status**: Pain, swelling, warmth
     - **Anticoagulation safety**: Bleeding signs, bruising, medication adherence

3. **Patient Task Compliance**
   - Anticoagulation adherence (CRITICAL - gaps increase PE risk)
   - Daily ambulation plan (prevents clot extension, reduces PTS risk)
   - Limb elevation
   - Compression stocking use (if prescribed, typically after acute phase)

---

## Alert Thresholds & Escalations

See **[Universal Alert Thresholds](../../shared/alert-thresholds.md)** for complete table.

### DVT-Specific Critical Alerts (Pulmonary Embolism)

| Parameter | Threshold | Clinical Significance | Action |
|-----------|-----------|----------------------|--------|
| **SpO2** | <92% | **High probability of PE** | **URGENT**: Assess respiratory status, CT PE protocol, call 911 if massive PE |
| **Heart Rate** | >100 bpm + SOB | PE likely | **Urgent evaluation**: D-dimer (if not anticoagulated), imaging |
| **Respiratory Rate** | >20/min + dyspnea | PE concern | **Same-day evaluation**: Vital signs, SpO2 monitoring, consider imaging |
| **Systolic BP** | <90 mmHg + SOB | **Massive PE with shock** | **CALL 911**: Hemodynamic collapse, requires ICU, consider thrombolytics |
| **Temperature** | >38.5°C | Septic thrombophlebitis | **Urgent**: Blood cultures, broad-spectrum antibiotics |

### Symptom-Based PE Alerts (HIGH PRIORITY)
- **Sudden dyspnea**: Classic PE presentation - **urgent evaluation**
- **Pleuritic chest pain** (pain with breathing): PE with infarction - **urgent**
- **Hemoptysis**: PE with pulmonary infarction - **urgent**
- **Dizziness + tachycardia + dyspnea**: Massive PE - **EMERGENT (911)**

### Bleeding Alerts (Anticoagulation Safety)
- **Hematuria** (blood in urine): Hold anticoagulation, urgent evaluation
- **Melena** (dark stools) or hematochezia (bloody stools): **GI bleeding** - hold anticoagulation, urgent evaluation
- **Hematemesis** (vomiting blood): **Upper GI bleed** - **call 911**
- **Intracranial hemorrhage** symptoms (severe headache, confusion, focal neuro): **CALL 911**

---

## Care Coordination

### Telemedicine/Virtual Visits
- **Daily check-ins** during first 72 hours (high PE risk period)
- **Every 2 days** thereafter if stable
- **Ad-hoc visits** for anticoagulation management, PE evaluation

### Interdisciplinary Task Management
- **Phlebotomy**: Home blood draws for PT/INR (if on warfarin), CBC (check Hgb for bleeding)
- **Anticoagulation Administration**: RN visits for subcutaneous heparin/LMWH injections (if bridging)
- **Ultrasound**: Repeat venous ultrasound if clinical worsening (assess clot extension)

---

## Treatment Protocol

### Anticoagulation Regimen

#### Initial Therapy (Days 1-5)
**Option 1: Direct Oral Anticoagulants (DOACs)** - Preferred for most patients
- **Rivaroxaban**: 15mg PO BID x21 days, then 20mg daily
- **Apixaban**: 10mg PO BID x7 days, then 5mg BID
- **Dabigatran**: Requires 5 days parenteral anticoagulation first, then 150mg BID
- **Edoxaban**: Requires 5 days parenteral anticoagulation first, then 60mg daily

**Advantages**: No monitoring, fixed dose, rapid onset
**Disadvantages**: Renal dosing required, no routine reversal agent (except dabigatran)

**Option 2: Warfarin (with heparin bridge)**
- **Warfarin**: Start 5mg PO daily, adjust to INR goal 2-3
- **Plus bridging anticoagulation** (until INR therapeutic x2 consecutive days):
  - Low molecular weight heparin (LMWH): Enoxaparin 1mg/kg SC BID, OR
  - Unfractionated heparin: Bolus + infusion (requires aPTT monitoring)

**Advantages**: Reversible (vitamin K), cheap, extensive experience
**Disadvantages**: Requires INR monitoring, food/drug interactions, slow onset

#### Duration of Anticoagulation
- **Provoked DVT** (surgery, trauma, immobilization): 3 months
- **Unprovoked DVT** (no clear trigger): 3-6 months minimum, consider extended
- **Recurrent DVT**: Indefinite anticoagulation
- **Active cancer**: Extended anticoagulation (often LMWH)

### Monitoring During Anticoagulation
- **Warfarin**: INR every 2-3 days initially, then weekly once stable, then monthly
- **DOACs**: No routine monitoring, but check renal function periodically
- **CBC**: Baseline and as needed (monitor Hgb for occult bleeding)
- **Bleeding assessment**: Daily via questionnaire + patient report

### Non-Pharmacologic Management
- **Ambulation**: Encourage walking (prevents clot extension, reduces PTS risk)
  - OLD dogma: bed rest for DVT (INCORRECT - ambulation is safe and beneficial)
- **Leg elevation**: When resting, elevate affected limb above heart level
- **Compression stockings**: Graduated 30-40 mmHg - start after acute phase (not immediately)
- **Hydration**: Adequate fluid intake (prevents hemoconcentration)

---

## Complications to Monitor

### Pulmonary Embolism (PE)
- **Most feared complication**: ~50% of untreated proximal DVT develop PE
- **Risk highest in first 72 hours** of diagnosis
- **Diagnosis**: CT pulmonary angiography (CTPA) - gold standard
- **Management**:
  - **Submassive PE** (stable): Continue anticoagulation
  - **Massive PE** (hemodynamic instability): **Hospital transfer**, thrombolytics, embolectomy

### Phlegmasia Cerulea Dolens (Massive DVT)
- **Rare but limb-threatening**: Massive venous occlusion → venous gangrene
- **Signs**: Severe pain, massive swelling, blue/purple discoloration, absent pulses
- **Management**: **Urgent vascular surgery consult**, catheter-directed thrombolysis

### Post-Thrombotic Syndrome (PTS)
- **Chronic complication**: 20-50% of DVT patients develop within 2 years
- **Signs**: Chronic leg pain, swelling, skin changes, venous ulcers
- **Prevention**: Early ambulation, compression stockings, anticoagulation

### Bleeding (Major Complication of Anticoagulation)
- **Major bleeding** rate: ~2-3% per year on anticoagulation
- **Risk factors**: Age >75, prior bleeding, cancer, renal failure, concomitant antiplatelet therapy
- **Management**: Hold anticoagulation, reversal agent if severe (vitamin K, PCC, idarucizumab)

---

## Comorbidity Management

See **[Comorbidity Matrix](../../shared/comorbidity-matrix.md)** for detailed guidance.

### Common DVT Comorbidities
- **DVT + CHF**: Differentiate leg swelling (bilateral CHF vs unilateral DVT); weight gain suggests CHF
- **DVT + COPD**: Both cause dyspnea - PE vs COPD exacerbation difficult to distinguish
- **DVT + Cancer**: Higher VTE recurrence risk; consider LMWH over warfarin/DOACs

---

## Transition to Post-Acute Care

### Discharge Readiness Criteria
- ✅ Therapeutic anticoagulation achieved (INR 2-3 if warfarin, or on DOAC ≥48hrs)
- ✅ No PE symptoms (no dyspnea, normal SpO2, no chest pain)
- ✅ Limb symptoms stable or improving (pain, swelling decreasing)
- ✅ No bleeding complications
- ✅ Patient educated on anticoagulation (adherence, bleeding signs, diet restrictions if warfarin)
- ✅ Has anticoagulation medication supply
- ✅ Follow-up arranged (hematology or primary care for INR monitoring if warfarin)

### Handoff to Post-Acute
See **[Transition to Post-Acute](./transition-to-postacute.md)** for full protocol.

**Key Handoff Information**:
- Anticoagulant regimen (drug, dose, duration planned)
- INR monitoring schedule (if warfarin)
- Date DVT diagnosed (calculate duration of therapy)
- Provoked vs unprovoked DVT (affects duration decision)
- Bleeding risk assessment
- Compression stocking prescription status

---

## References
- Source: Carepath DVT Acute Care Pathway SOP
- American College of Chest Physicians (ACCP) Antithrombotic Guidelines
- Wells Score: Clinical prediction rule for DVT
- PERC Rule: PE rule-out criteria

**Related Skills**: After stabilization, patient transitions to `carepath-postacute` skill for 30-day anticoagulation monitoring and PE prevention.
