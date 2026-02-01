---
name: carepath-postacute
description: |
  Clinical decision support for post-acute remote patient monitoring across 7 disease pathways (CHF, COPD, Pneumonia, HTN, Diabetes, DVT, COVID-19).
  
  **Triggers**: "post-acute care", "post-discharge", "readmission prevention", "30-day monitoring", "hospital discharge", "home monitoring", "chronic disease management", "transitional care", "recovery monitoring"
  
  Provides protocol guidance for post-discharge readmission prevention including device selection, monitoring thresholds, alert escalation, daily patient tasks, complication surveillance, and transition planning.
---

# Carepath Post-Acute Care Pathways

**Version**: 1.0  
**Optimized for**: Qwen-Pro API + OpenCode  
**Coverage**: 7 post-acute disease pathways

---

## Quick Reference: Disease Selection

Use this table to quickly identify which post-acute care pathway to reference based on patient's discharge diagnosis:

| Disease | Post-Acute Indication | Duration | Key Devices | Critical Alert Threshold |
|---------|----------------------|----------|-------------|--------------------------|
| **[CHF](references/chf-postacute.md)** | Post-discharge readmission prevention | 30 days | Everion armband, weight scale, BP cuff | Weight gain ≥3 lbs/3 days; SpO2 <92%; KCCQ score drop ≥10 points |
| **[COPD](references/copd-postacute.md)** | Post-exacerbation recovery, prevent re-exacerbation | 90 days | Everion armband, pulse ox, BP cuff, spirometer | SpO2 <88%; CAT score ≥20 (worsening symptoms); Increased purulent sputum |
| **[Pneumonia](references/pneumonia-postacute.md)** | Post-CAP recovery, prevent relapse | 30 days | Everion armband, pulse ox, thermometer | Fever recurrence >38°C; SpO2 <92%; New/worsening dyspnea |
| **[HTN](references/htn-postacute.md)** | BP optimization after hypertensive urgency | 30 days | BP cuff, Everion armband (optional) | SBP >160 or DBP >100 mmHg (sustained); End-organ damage symptoms |
| **[Diabetes](references/diabetes-postacute.md)** | Post-DKA/HHS stabilization, prevent recurrence | 30 days | CGM or glucometer, ketone meter, Everion armband | Glucose <70 or >250 mg/dL; Ketones >0.6 mmol/L; Recurrent DKA symptoms |
| **[DVT](references/dvt-postacute.md)** | Anticoagulation monitoring, VTE prevention | 90 days | INR monitor (if warfarin), Everion armband | New chest pain/dyspnea (PE); Bleeding (major); INR >4.0 or <2.0 (if warfarin) |
| **[COVID-19](references/covid-postacute.md)** | Post-diagnosis monitoring, long COVID surveillance | 14 days | Everion armband, thermometer | SpO2 <92%; Emergency symptoms (chest pain, confusion); Fever >39°C |

---

## When to Use This Skill

### Post-Acute Care Pathway Criteria (vs Acute)

**Use `carepath-postacute` skill when patient**:

1. **Recently discharged from hospital** OR **completed acute care pathway**:
   - Within 30 days of hospital discharge for acute illness
   - Transitioned from acute care pathway (no longer requires IV therapy)
   - At high risk for readmission (chronic disease, recent exacerbation)

2. **On oral therapy only** (no IV medications):
   - Oral diuretics (CHF)
   - Oral antibiotics completing course (Pneumonia)
   - Oral antihypertensives (HTN)
   - Subcutaneous insulin (Diabetes)
   - Oral anticoagulation (DVT)
   - No active IV treatment needed (COVID)

3. **Lower-intensity monitoring needs** (vs acute care):
   - Daily patient tasks (questionnaires, vital checks) but NOT continuous clinical team review
   - Care team reviews q2-3 days (or when alerts trigger)
   - Focus on trend detection (worsening symptoms over days) vs acute deterioration (within hours)

4. **Readmission prevention focus**:
   - Medication adherence monitoring
   - Early detection of decompensation before ER/hospital needed
   - Patient education on self-management
   - Chronic disease optimization

**Do NOT use for**:
- Active acute illness requiring IV therapy → Use `carepath-acute` skill instead
- Stable chronic disease (>90 days post-event, no recent hospitalization) → Primary care
- Patients still hospitalized → Inpatient care protocols

---

## How to Use This Skill

### Step 1: Identify Disease Pathway

Match patient's discharge diagnosis to one of 7 pathways using Quick Reference table above.

**For patients with multiple comorbidities**:
- Select pathway based on **PRIMARY DISCHARGE DIAGNOSIS** (reason for recent hospitalization)
- Example: Patient with CHF + COPD hospitalized for CHF exacerbation → Use **CHF post-acute pathway**, reference COPD comorbidity considerations
- See [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md) for cross-disease interactions

### Step 2: Verify Eligibility

Open disease-specific post-acute pathway reference and confirm:
- Patient meets **inclusion criteria** (age, diagnosis, functional capacity)
- Patient does NOT meet any **exclusion criteria** (usually indicates ongoing acute care needs or palliative focus)

### Step 3: Protocol Implementation

Each post-acute pathway reference provides structured sections:

1. **Devices & Monitoring Equipment**: Which connected devices to deploy for home use
2. **Physiologic Monitoring**: What vital signs/parameters to track and how often
3. **Daily Patient Tasks**: What patient must do each day (questionnaires, vitals, medication logging)
4. **Patient Education**: Disease-specific education modules for self-management
5. **Alerts/Thresholds/Escalations**: When to escalate to care team, urgent evaluation, or ER
6. **Complications or Adverse Events**: What to watch for (readmission triggers, medication side effects)
7. **Comorbidity Considerations**: How co-existing diseases modify the protocol
8. **Transition Criteria**: When to complete program vs escalate back to acute care

### Step 4: Alert Management

**Universal alert thresholds** are documented in [`shared/alert-thresholds.md`](../shared/alert-thresholds.md).

**Disease-specific threshold modifications** are in each pathway reference (e.g., COPD patients tolerate lower SpO2, diabetes has glucose-specific thresholds).

**Escalation levels** (same as acute care, but applied differently):
- 🔴 **CRITICAL (Red)**: Immediate response required (<1 hour) - high risk, possible ER
- 🟠 **URGENT (Orange)**: Response within 24 hours - worsening trend, intervention needed
- 🟡 **ADVISORY (Yellow)**: Response within 2-3 days - early warning, patient education/reminder

**Note**: Post-acute alerts are generally LESS urgent than acute care (hours/days response vs minutes/hours).

### Step 5: Questionnaires & Symptom Monitoring

Daily patient-reported symptom questionnaires are in [`shared/questionnaires/`](../shared/questionnaires/):

- [`chf-questionnaire.md`](../shared/questionnaires/chf-questionnaire.md) - Daily fluid status + KCCQ-12 quality of life
- [`copd-questionnaire.md`](../shared/questionnaires/copd-questionnaire.md) - Daily exacerbation symptoms + CAT score
- [`pneumonia-questionnaire.md`](../shared/questionnaires/pneumonia-questionnaire.md) - Infection symptom surveillance
- [`htn-questionnaire.md`](../shared/questionnaires/htn-questionnaire.md) - Hypertensive emergency symptom surveillance
- [`diabetes-questionnaire.md`](../shared/questionnaires/diabetes-questionnaire.md) - Hypo/hyperglycemia assessment
- [`dvt-questionnaire.md`](../shared/questionnaires/dvt-questionnaire.md) - PE warning signs + anticoagulation safety
- [`covid-questionnaire.md`](../shared/questionnaires/covid-questionnaire.md) - 911 criteria + respiratory/systemic symptoms

Each questionnaire includes:
- Questions with response options
- Scoring/interpretation guidelines
- Clinical decision rules (when to escalate)

---

## Disease Pathway References

### 1. CHF (Congestive Heart Failure) Post-Acute Care

**File**: [`references/chf-postacute.md`](references/chf-postacute.md)

**Objective**: Reduce 30-day readmission risk (national ~25%, target <20%) through home monitoring and early intervention.

**Duration**: 30 days post-discharge

**Eligibility**:
- Age 21-75, CHF diagnosis, improving congestion, off O2, on oral diuretics
- ✗ Exclusions: Stage D, LVAD, inotrope-dependent, severe PH, unable to tolerate GDMT

**Key Devices**:
- **Everion armband** (continuous HR, RR, SpO2, skin temp, activity)
- **Weight scale** (MOST IMPORTANT - #1 CHF readmission predictor)
- **BP cuff** (for GDMT titration)

**Critical Alerts**:
- Weight gain ≥3 lbs/3 days or ≥5 lbs/week
- SpO2 <92%
- KCCQ-12 score drop ≥10 points (quality of life deterioration)
- New/worsening orthopnea, PND, edema

**Daily Patient Tasks**:
- Morning weight (same time, same scale, after urination, before breakfast)
- Daily CHF questionnaire (fluid status, dyspnea, edema)
- BP check (if on GDMT titration)
- Medication logging

**Patient Education**:
- Sodium restriction (<2g/day)
- Fluid restriction (if applicable, usually <2L/day)
- GDMT medication importance (ACEi/ARB/ARNI, beta-blocker, MRA, SGLT2i)
- When to call provider (weight gain, worsening dyspnea)

**Complications**: Readmission for decompensation (20-25% at 30 days), cardiorenal syndrome, medication non-adherence, electrolyte abnormalities

**Transition**: Complete 30-day program if stable → PCP follow-up. Escalate to acute care if decompensation (weight gain, worsening dyspnea, hypoxemia).

---

### 2. COPD Post-Acute Care

**File**: [`references/copd-postacute.md`](references/copd-postacute.md)

**Objective**: Prevent re-exacerbation and hospital readmission (50% re-exacerbate within 90 days) through monitoring and early intervention.

**Duration**: 90 days post-exacerbation (longer than most pathways due to high re-exacerbation rate)

**Eligibility**:
- Confirmed COPD diagnosis, recent AECOPD, clinically stable, off IV therapy
- ✗ Exclusions: Chronic respiratory failure requiring mechanical ventilation, end-stage COPD (hospice-appropriate)

**Key Devices**:
- **Everion armband** (continuous HR, RR, SpO2)
- **Pulse oximeter** (backup/spot checks)
- **BP cuff** (medication monitoring)
- **Spirometer** (optional - for FEV1 trending)

**Critical Alerts**:
- SpO2 <88% (COPD target 88-92%, NOT 95%+)
- CAT score ≥20 (significant symptom burden, exacerbation risk)
- Increased purulent sputum production (exacerbation sign)
- RR >22/min sustained

**Daily Patient Tasks**:
- Daily COPD questionnaire (dyspnea, cough, sputum color/volume)
- Weekly CAT score (symptom assessment)
- SpO2 check (if not wearing Everion continuously)
- Inhaler technique verification (via app video submission)

**Patient Education**:
- Inhaler technique (correct use critical for efficacy)
- Exacerbation action plan (when to start rescue pack: corticosteroids + antibiotics)
- Smoking cessation (if applicable)
- Pulmonary rehabilitation referral

**Complications**: Re-exacerbation (50% within 90 days), pneumonia, PE, respiratory failure, depression/anxiety

**Transition**: Complete 90-day program if no exacerbations → PCP maintenance. Escalate to acute care if exacerbation criteria met (worsening dyspnea, purulent sputum, increased cough).

---

### 3. Pneumonia Post-Acute Care

**File**: [`references/pneumonia-postacute.md`](references/pneumonia-postacute.md)

**Objective**: Ensure complete recovery from pneumonia, prevent relapse (5-10% relapse rate), monitor for complications.

**Duration**: 30 days post-discharge

**Eligibility**:
- Confirmed CAP, completed acute IV antibiotic phase, afebrile >48 hrs, clinically improving
- ✗ Exclusions: Persistent fever, severe hypoxemia (SpO2 <90% on 4L NC), immunocompromised with high relapse risk

**Key Devices**:
- **Everion armband** (continuous HR, RR, SpO2, temp)
- **Pulse oximeter** (backup/spot checks)
- **Thermometer** (twice daily temp checks)

**Critical Alerts**:
- Fever recurrence >38°C (relapse or complication)
- SpO2 <92%
- New or worsening dyspnea
- Pleuritic chest pain (possible empyema or PE)

**Daily Patient Tasks**:
- Twice daily temperature (morning, evening)
- Daily pneumonia questionnaire (cough, dyspnea, chest pain, sputum)
- SpO2 check
- Antibiotic adherence (if completing oral course)

**Patient Education**:
- Complete full antibiotic course (even if feeling better)
- Pneumonia recovery timeline (4-6 weeks for full recovery, fatigue normal)
- When to call provider (fever returns, worsening dyspnea, chest pain)
- Vaccination (pneumococcal, influenza if not up to date)

**Complications**: Relapse/treatment failure (5-10%), pleural effusion/empyema, lung abscess, sepsis, post-pneumonia fatigue syndrome

**Transition**: Complete 30-day program if fully recovered → PCP follow-up CXR at 6 weeks (ensure resolution). Escalate to acute care if relapse (fever, worsening symptoms).

---

### 4. HTN (Hypertension) Post-Acute Care

**File**: [`references/htn-postacute.md`](references/htn-postacute.md)

**Objective**: Optimize BP control to <130/80 mmHg after hypertensive urgency, prevent end-organ damage, medication adherence.

**Duration**: 30 days (BP stabilization period)

**Eligibility**:
- Recent hypertensive urgency (SBP ≥180 or DBP ≥110 without end-organ damage), now stabilized on oral antihypertensives
- ✗ Exclusions: Prior hypertensive emergency (with end-organ damage), resistant HTN requiring specialist management

**Key Devices**:
- **BP cuff** (ESSENTIAL - multiple daily checks initially)
- **Everion armband** (optional - for HR monitoring, activity correlation)

**Critical Alerts**:
- SBP >160 mmHg or DBP >100 mmHg (sustained on 3+ readings)
- Symptoms of end-organ damage (severe headache, vision changes, chest pain, confusion, dyspnea)
- SBP <100 mmHg or symptomatic hypotension (over-treatment)

**Daily Patient Tasks**:
- **BP checks**: Twice daily (morning, evening) initially → daily once stable
- Medication logging (adherence critical)
- Side effect monitoring questionnaire (dizziness, fatigue, cough, edema)

**Patient Education**:
- Medication adherence importance (most common cause of uncontrolled HTN)
- Home BP measurement technique (proper cuff size, seated 5 min, arm at heart level)
- Lifestyle modifications (sodium <2g/day, DASH diet, weight loss, exercise, limit alcohol)
- When to seek urgent care (SBP >180, chest pain, severe headache, vision changes)

**Complications**: Hypertensive emergency (stroke, MI, acute CHF, aortic dissection), medication side effects, non-adherence

**Transition**: Complete 30-day program if BP controlled <130/80 mmHg on stable med regimen → PCP long-term management. Escalate to acute care if hypertensive urgency recurs (SBP ≥180).

---

### 5. Diabetes Post-Acute Care

**File**: [`references/diabetes-postacute.md`](references/diabetes-postacute.md)

**Objective**: Prevent DKA/HHS recurrence (20% re-admission rate in 30 days), optimize insulin regimen, ensure safe glucose control.

**Duration**: 30 days post-discharge

**Eligibility**:
- Recent DKA or HHS, now resolved (glucose <200 mg/dL, pH >7.3, anion gap closed), on stable subcutaneous insulin regimen
- ✗ Exclusions: Persistent severe hyperglycemia (glucose >400 mg/dL), recurrent DKA (>2 episodes in 6 months requiring specialist care)

**Key Devices**:
- **CGM (continuous glucose monitor)** OR **glucometer** (QID checks minimum: fasting, pre-lunch, pre-dinner, bedtime)
- **Ketone meter** (blood ketones more accurate than urine)
- **Everion armband** (optional - for HR, activity correlation with glucose)

**Critical Alerts**:
- Glucose <70 mg/dL (hypoglycemia)
- Glucose >250 mg/dL with ketones >0.6 mmol/L (DKA risk)
- Glucose >400 mg/dL (HHS risk)
- Recurrent DKA symptoms (nausea, vomiting, abdominal pain, fruity breath)

**Daily Patient Tasks**:
- Glucose checks (QID if glucometer, review CGM trends if CGM)
- Ketone check if glucose >250 mg/dL
- Daily diabetes questionnaire (hypo/hyper symptoms, DKA warning signs)
- Insulin dose logging (basal + bolus)
- Carb counting (meal logging)

**Patient Education**:
- DKA/HHS triggers (infection, medication non-adherence, new stressors)
- Sick day management (NEVER stop insulin, check ketones if glucose >250, call provider)
- Hypoglycemia recognition and treatment (15-15 rule: 15g fast-acting carb, recheck in 15 min)
- Insulin injection technique
- When to go to ER (persistent vomiting, ketones >1.5, glucose >400, altered mental status)

**Complications**: Recurrent DKA/HHS (20% in 30 days), severe hypoglycemia, infection (poorly controlled glucose impairs immune function)

**Transition**: Complete 30-day program if glucose controlled (80% readings 70-180 mg/dL, A1c trending down) → Endocrinology or PCP long-term management. Escalate to acute care if recurrent DKA/HHS.

---

### 6. DVT (Deep Vein Thrombosis) Post-Acute Care

**File**: [`references/dvt-postacute.md`](references/dvt-postacute.md)

**Objective**: Prevent PE (most feared complication), ensure safe anticoagulation, prevent DVT extension/recurrence.

**Duration**: 90 days (minimum anticoagulation duration for provoked DVT, may extend to 6-12 months or lifelong)

**Eligibility**:
- Acute DVT confirmed by Doppler ultrasound, transitioned to oral anticoagulation (warfarin or DOAC), no PE or stable PE
- ✗ Exclusions: High-risk PE (massive PE, hemodynamic instability), active bleeding, severe renal failure (CrCl <15 requiring alternative anticoagulation)

**Key Devices**:
- **INR monitor** (if on warfarin - weekly INR checks, target 2-3)
- **Everion armband** (HR, RR, SpO2 monitoring for PE detection)

**Critical Alerts**:
- **New chest pain, dyspnea, tachycardia** (PE symptoms) → URGENT evaluation
- **Bleeding** (major: GI bleed, hematuria, intracranial hemorrhage; minor: bruising, nosebleeds)
- **INR >4.0 or <2.0** (if on warfarin - out of therapeutic range)
- Leg swelling worsening (DVT extension)

**Daily Patient Tasks**:
- Daily DVT questionnaire (PE symptoms, bleeding symptoms, leg swelling)
- INR check (weekly if warfarin, log result in app)
- Anticoagulation adherence logging
- Bleeding surveillance (gum bleeding, bruising, blood in urine/stool)

**Patient Education**:
- Anticoagulation safety (avoid high-risk activities, contact sports, alcohol moderation)
- Drug/food interactions (warfarin: vitamin K foods, many drug interactions; DOACs: fewer interactions)
- When to go to ER (chest pain, severe dyspnea, coughing blood, severe bleeding, severe headache)
- DVT prevention (compression stockings if post-thrombotic syndrome, leg elevation, avoid prolonged immobility)

**Complications**: PE (10-20% of DVT patients), post-thrombotic syndrome (chronic leg swelling/pain), bleeding (anticoagulation complication), DVT recurrence

**Transition**: Complete 90-day program if stable on anticoagulation, no PE, no bleeding → Hematology or PCP long-term anticoagulation management (duration decision: 3 months vs extended/lifelong). Escalate to acute care if PE develops.

---

### 7. COVID-19 Post-Acute Care

**File**: [`references/covid-postacute.md`](references/covid-postacute.md)

**Objective**: Monitor critical deterioration window (days 5-10), prevent complications (bacterial superinfection, VTE, myocarditis), detect long COVID (symptoms >4 weeks).

**Duration**: 14 days (shorter than most post-acute pathways - acute viral illness vs chronic disease)

**Eligibility**:
- Confirmed COVID-19 diagnosis, stable/improving symptoms, SpO2 ≥92% on ≤4L NC (or <6 hrs/day O2)
- ✗ Exclusions: Severe hypoxemia (SpO2 <92% on 4L NC), respiratory failure, altered mental status, hemodynamic instability

**Key Devices**:
- **Everion armband** (continuous HR, RR, SpO2, skin temp, activity)
- **Thermometer** (twice daily temp checks)

**Critical Alerts**:
- **SpO2 <92%** (silent hypoxemia common in COVID)
- **Emergency symptoms** (blue lips, severe chest pain, confusion) → 911
- RR >25/min
- Fever >39°C (biphasic fever may indicate bacterial superinfection)

**Daily Patient Tasks**:
- **Twice daily temperature** (morning, evening)
- Daily COVID questionnaire (Section A: 911 criteria, Section B: respiratory symptoms, Section C: systemic symptoms)
- SpO2 monitoring (Everion continuous + spot checks)
- Activity tracking (sudden decrease may indicate decompensation)

**Patient Education**:
- Critical window days 5-10 (patients often feel better early, then deteriorate - do NOT reduce monitoring)
- Silent hypoxemia (severe low oxygen WITHOUT shortness of breath - must check SpO2 even if feeling OK)
- Prone positioning (lying on stomach improves SpO2 by 2-5%)
- When to call 911 (emergency warning signs from questionnaire Section A)
- Isolation criteria (CDC guidelines)
- Long COVID (symptoms >4 weeks - fatigue, brain fog, dyspnea, POTS)

**Complications**: Progressive COVID pneumonia, ARDS, bacterial superinfection (days 7-14), VTE (DVT/PE - COVID is hypercoagulable), myocarditis, stroke, long COVID (20-30% develop persistent symptoms)

**Transition**: Complete 14-day program if recovered (afebrile >48 hrs, SpO2 >95% on room air, symptom improvement) → PCP follow-up. **Screen for long COVID** at day 14 - if symptoms persist >4 weeks, refer to multidisciplinary long COVID clinic. Escalate to acute care if deterioration (SpO2 <92%, respiratory distress, fever recurrence suggesting superinfection).

---

## Shared Resources

All post-acute care pathways reference these shared knowledge bases:

### 1. Alert Thresholds & Escalation Protocols

**File**: [`shared/alert-thresholds.md`](../shared/alert-thresholds.md)

Universal vital sign thresholds for:
- SpO2, heart rate, respiratory rate, blood pressure, temperature, weight, glucose
- 3-tier escalation (Critical/Urgent/Advisory)
- Disease-specific threshold modifications (e.g., COPD SpO2 target 88-92%)

**Note**: Post-acute thresholds may be more LENIENT than acute care (allowing time for patient self-management and outpatient intervention before escalation).

### 2. Monitoring Devices Catalog

**File**: [`shared/devices.md`](../shared/devices.md)

Complete specifications for all connected devices:
- Everion armband (lighter, longer battery than VitalPatch - preferred for post-acute)
- Weight scales (Welch Allyn RPM-SCALE100, ForaCare W550)
- BP cuffs (Welch Allyn 1700, Omron BP7000)
- Pulse oximeters (Nonin 3230)
- Glucometers, CGMs, ketone meters
- INR monitors (CoaguChek)
- Thermometers

Includes: Device accuracy, setup instructions, troubleshooting, pathway applicability

### 3. Disease-Specific Questionnaires

**Directory**: [`shared/questionnaires/`](../shared/questionnaires/)

7 daily symptom questionnaires with scoring, interpretation, and clinical decision rules (same as acute care, but interpreted differently for post-acute context):

- CHF: Fluid status + KCCQ-12 quality of life (QoL drop ≥10 points = readmission risk)
- COPD: Exacerbation symptoms + CAT score (CAT ≥20 = high symptom burden)
- Pneumonia: Infection symptom surveillance (fever recurrence = relapse)
- HTN: Hypertensive emergency symptoms (headache, vision changes, chest pain)
- Diabetes: Hypo/hyperglycemia assessment (glucose trends, DKA warning signs)
- DVT: PE warning signs + anticoagulation safety (bleeding surveillance)
- COVID: 911 criteria + respiratory/systemic symptoms (silent hypoxemia detection)

### 4. Comorbidity Interaction Matrix

**File**: [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md)

Cross-disease considerations for patients with multiple conditions:
- CHF + COPD: Dyspnea differentiation (BNP helpful), overlapping med contraindications (beta-blockers)
- CHF + HTN: BP targets (systolic goal <130, but avoid <100), GDMT overlap
- Diabetes + COVID: Hyperglycemia worsens outcomes, corticosteroids worsen glucose control
- COPD + Pneumonia: Exacerbation vs infection differentiation
- DVT + COVID: Hypercoagulability (prophylactic anticoagulation consideration)
- HTN + Diabetes: Medication interactions (ACEi/ARB beneficial for both)
- And 25+ other combinations

---

## Transition Management

### Transition FROM Acute Care (Step-Down)

**File**: [`references/transition-from-acute.md`](references/transition-from-acute.md)

When patient completes acute care pathway and steps down to post-acute monitoring:

**Process**:
1. Confirm acute care completion criteria met (see acute pathway transition criteria)
2. Update medication list (IV → oral conversions documented)
3. Adjust device requirements:
   - May discontinue VitalPatch → switch to Everion armband (lighter, longer battery)
   - Continue disease-critical devices (weight scale for CHF, glucometer for diabetes, etc.)
4. Lower alert threshold sensitivity:
   - Post-acute allows more time for patient self-management before escalation
   - Critical alerts still trigger urgent response, but urgent/advisory alerts may have longer response times
5. Handoff from acute care team to post-acute care team:
   - Summary of acute care course (treatments given, complications, medication changes)
   - Remaining post-acute monitoring duration (e.g., if acute care was 5 days, post-acute continues for remaining 25 days to complete 30-day total)
6. Patient education on transition:
   - Explain reduced monitoring intensity (still daily tasks, but less frequent care team contact)
   - Reinforce self-management responsibilities (medication adherence, recognizing warning signs)

**Example**: CHF patient completed 7 days of acute care (IV diuresis, now euvolemic, switched to oral furosemide) → Steps down to post-acute CHF pathway for remaining 23 days of 30-day monitoring period. VitalPatch removed, Everion armband deployed. Focus shifts from active diuresis to readmission prevention via weight/symptom monitoring.

---

### Transition TO Acute Care (Escalation)

**When patient on post-acute pathway deteriorates and requires acute care re-admission**:

**Indications for escalation** (see each disease pathway for specific criteria):
- **CHF**: Worsening dyspnea + weight gain (fluid overload requiring IV diuresis)
- **COPD**: Exacerbation (worsening dyspnea, purulent sputum requiring IV/oral corticosteroids)
- **Pneumonia**: Relapse (fever recurrence, worsening symptoms requiring IV antibiotics)
- **HTN**: Hypertensive urgency recurrence (SBP ≥180 despite oral meds)
- **Diabetes**: Recurrent DKA/HHS (glucose >250 + ketones, or glucose >400)
- **DVT**: PE development (chest pain, dyspnea, tachycardia requiring admission)
- **COVID**: Respiratory decompensation (SpO2 <92%, severe dyspnea requiring hospitalization)

**Escalation Process**:
1. Alert triggered (critical threshold met)
2. Care team urgent evaluation (video visit or phone call within 1 hour)
3. Decision: Can manage outpatient (medication adjustment, closer monitoring) OR requires acute care/ED
4. If acute care needed:
   - Immediate physician notification
   - Arrange ED evaluation or direct hospital-at-home acute care admission
   - Transfer physiologic data trends (helps acute team understand trajectory)
   - Document post-acute care interventions attempted (shows progression despite outpatient management)
5. Patient enters acute care pathway, post-acute monitoring paused
6. After acute care completion, may return to post-acute pathway (see "Transition FROM Acute Care" above)

---

### Program Completion (Successful Discharge)

**When patient successfully completes post-acute monitoring period without complications**:

**Criteria for completion** (all must be met):
1. **Full monitoring duration completed**:
   - CHF: 30 days
   - COPD: 90 days
   - Pneumonia: 30 days
   - HTN: 30 days
   - Diabetes: 30 days
   - DVT: 90 days (may continue anticoagulation longer, but remote monitoring phase ends)
   - COVID: 14 days
2. **Clinical stability**:
   - No critical alerts in past 7 days
   - Vital signs at acceptable baseline (disease-specific)
   - Symptom questionnaire scores stable or improving
3. **Medication optimized**:
   - GDMT maximized (CHF)
   - Inhaler technique verified (COPD)
   - Antibiotic course completed (Pneumonia)
   - BP controlled on stable regimen (HTN)
   - Glucose controlled on stable insulin regimen (Diabetes)
   - Therapeutic anticoagulation achieved (DVT)
   - Recovery confirmed (COVID)
4. **Patient education completed**:
   - All education modules reviewed
   - Self-management plan documented
   - When to contact provider understood

**Completion Process**:
1. Final video visit with care team
2. Discharge summary generated (monitoring data trends, complications encountered, medication changes)
3. Transition to PCP for long-term chronic disease management
4. Follow-up appointments scheduled:
   - CHF: Cardiology within 2-4 weeks
   - COPD: Pulmonology within 4 weeks, pulmonary rehab referral
   - Pneumonia: PCP within 2 weeks, CXR at 6 weeks to confirm resolution
   - HTN: PCP within 2-4 weeks for continued BP monitoring
   - Diabetes: Endocrinology within 2-4 weeks for A1c check, insulin adjustment
   - DVT: Hematology within 4 weeks to discuss anticoagulation duration (3 months vs extended)
   - COVID: PCP within 2 weeks, long COVID screening (if symptoms persist >4 weeks → multidisciplinary clinic referral)
5. Device return or patient keeps for future use (practice-dependent)

---

## Shared Resources (Continued)

### Patient Education Framework

All post-acute pathways include structured patient education delivered via in-app modules:

**Core Education Topics** (universal across all pathways):
1. **Disease pathophysiology** (simplified explanation)
2. **Medication purpose and adherence** (why each medication is critical)
3. **Warning signs** (when to contact provider vs 911)
4. **Self-management strategies** (lifestyle modifications, symptom monitoring)
5. **Device usage** (how to properly use monitoring equipment)

**Disease-Specific Education** (see each pathway reference for details):
- CHF: Sodium/fluid restriction, daily weights, GDMT importance
- COPD: Inhaler technique, exacerbation action plan, smoking cessation
- Pneumonia: Antibiotic completion, recovery timeline, vaccination
- HTN: Home BP measurement, lifestyle modifications, medication adherence
- Diabetes: Insulin technique, sick day management, hypo/hyperglycemia recognition
- DVT: Anticoagulation safety, PE symptoms, compression stocking use
- COVID: Critical window days 5-10, silent hypoxemia, prone positioning, long COVID

**Education Delivery**:
- **Timing**: Staggered over monitoring period (not all day 1 - avoids overwhelming patient)
- **Format**: Short videos (2-3 min), infographics, interactive quizzes
- **Reinforcement**: Care team video visits review key concepts, address misconceptions
- **Engagement tracking**: Monitor which modules completed, quiz scores (identifies knowledge gaps)

---

## Clinical Pearls

### Universal Post-Acute Care Principles

1. **Readmission prevention is PRIMARY goal** - Early detection of decompensation before ER visit needed. Post-acute monitoring proven to reduce 30-day readmissions by 20-40%.

2. **Patient engagement is CRITICAL** - Post-acute care success depends on patient completing daily tasks (questionnaires, vitals). Non-compliance is early warning sign (may indicate worsening symptoms, depression, health literacy issues).

3. **Medication adherence monitoring** - 50% of readmissions due to medication non-adherence. Daily logging + pill counts + pharmacy refill tracking identify non-adherence early.

4. **Trend detection > single data point** - In post-acute care, a TREND (worsening weight over 3 days, gradually declining SpO2) is more meaningful than single abnormal reading (which may be device error or temporary).

5. **Lower monitoring intensity than acute care, but still structured** - Care team reviews q2-3 days (not daily like acute care), but patient still does daily tasks. This balance maintains safety while being sustainable for 30-90 day timeframes.

6. **Comorbidity amplification** - Patients with multiple chronic diseases have MUCH higher readmission risk. CHF + COPD = 40% readmission rate (vs 20-25% for CHF alone). Use comorbidity matrix religiously.

7. **Social determinants matter** - Medication non-adherence, missed appointments, device non-use often signal social issues (can't afford meds, transportation barriers, housing instability). Care coordination should address these.

8. **Telehealth is essential** - Post-acute care relies on video visits for urgent assessments, med adjustments, patient education. Avoids unnecessary ER visits while maintaining safety.

### Red Flags for Escalation (Post-Acute → Acute Care or ER)

**ANY of these → patient requires urgent evaluation, possible acute care pathway re-entry or ER**:

**Respiratory**:
- SpO2 <92% sustained (or <88% for COPD)
- Severe dyspnea at rest
- New chest pain (PE, MI, pneumonia complication)

**Cardiac**:
- Rapid weight gain (CHF: ≥5 lbs/week)
- New/worsening orthopnea, PND, edema
- Symptomatic hypotension (SBP <90 mmHg with dizziness)

**Neurological**:
- Confusion, disorientation (hypoxemia, stroke, hypoglycemia)
- Severe headache with vision changes (hypertensive emergency)

**Metabolic**:
- Glucose <70 mg/dL or >400 mg/dL
- Recurrent DKA symptoms (nausea, vomiting, abdominal pain, fruity breath)

**Hematologic**:
- Major bleeding (anticoagulation complication)
- New DVT/PE symptoms

**Infectious**:
- Fever >39°C (relapse, complication, superinfection)
- Sepsis signs (tachycardia, hypotension, altered mental status)

**If any red flag → DO NOT wait for routine care team review. Immediate outreach to patient, urgent video visit, consider ER referral.**

---

## Example Usage Scenarios

### Scenario 1: CHF Patient Post-Discharge

**Presentation**: 68F discharged 2 days ago after 5-day hospitalization for CHF exacerbation. Received IV furosemide, now on oral furosemide 40 mg BID. Home on Everion armband + weight scale + BP cuff.

**Decision Tree**:
1. Primary diagnosis: **CHF post-discharge**
2. **Use [`references/chf-postacute.md`](references/chf-postacute.md)**
3. Eligibility: Age 68 ✓, CHF diagnosis ✓, improving congestion ✓, off O2 ✓, on oral diuretics ✓
4. Monitoring duration: 30 days from discharge
5. Daily patient tasks:
   - **Morning weight** (most important - readmission predictor)
   - Daily CHF questionnaire (orthopnea, PND, edema, dyspnea)
   - BP check (for GDMT titration)
   - Medication logging
6. Critical alerts to watch for:
   - Weight gain ≥3 lbs/3 days or ≥5 lbs/week → Call patient same day, video visit, possible diuretic increase
   - SpO2 <92% → Urgent evaluation (pulmonary edema?)
   - KCCQ-12 score drop ≥10 points → Quality of life deteriorating, early readmission warning
7. Patient education (staggered delivery):
   - Day 1: Importance of daily weights (best predictor of fluid status)
   - Day 3: Sodium restriction <2g/day (fluid retention prevention)
   - Day 7: GDMT medication importance (ACEi, beta-blocker, MRA, SGLT2i reduce mortality)
   - Day 14: When to call provider (weight gain, worsening dyspnea, new edema)
8. **Day 12 alert**: Weight increased 4 lbs over past 3 days. Patient reports mild increased dyspnea, no orthopnea.
   - **Response**: Video visit same day. Assessment: Early fluid overload (not yet requiring hospitalization). Intervention: Increase furosemide to 60 mg BID x 3 days, recheck weight daily. If weight up another 2 lbs → consider acute care pathway re-entry (IV diuresis). Weight stabilized after 2 days → Crisis averted, readmission prevented.
9. Completes 30-day monitoring without further alerts → Discharge to cardiology for ongoing GDMT titration and long-term CHF management.

**Key insight**: Daily weight monitoring + early diuretic adjustment PREVENTED readmission. Without remote monitoring, patient would likely have presented to ER in another 5-7 days with severe fluid overload.

---

### Scenario 2: COPD Patient Post-Exacerbation with Pneumonia History (Comorbidity)

**Presentation**: 72M discharged 1 week ago after COPD exacerbation + pneumonia. Completed IV ceftriaxone (5 days), now on oral azithromycin (completing 7-day course). Prednisone taper completed. Baseline O2 2L NC (unchanged from pre-admission). History of 3 exacerbations in past year.

**Decision Tree**:
1. Primary diagnosis: **COPD post-exacerbation** (longer monitoring needed - 90 days)
2. Comorbidity: Recent pneumonia (monitor for relapse)
3. **Use [`references/copd-postacute.md`](references/copd-postacute.md)**, consult [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md) → COPD + Pneumonia section
4. Eligibility: COPD confirmed ✓, recent AECOPD ✓, clinically stable ✓, off IV therapy ✓
5. Monitoring duration: **90 days** (high re-exacerbation risk - 50% within 90 days, especially with 3+ exacerbations/year)
6. Deploy: Everion armband, pulse oximeter, BP cuff, thermometer (added due to recent pneumonia)
7. **Comorbidity modification**:
   - Add **twice daily temperature checks** (first 14 days to monitor for pneumonia relapse)
   - Lower threshold for fever alert (any temp >38°C → urgent evaluation, possible relapse)
   - Differentiation: Purulent sputum + fever = likely pneumonia relapse (not just COPD exacerbation) → needs antibiotics
8. Daily patient tasks:
   - Daily COPD questionnaire (dyspnea, cough, sputum color/volume)
   - Weekly CAT score (symptom burden assessment)
   - SpO2 check (target 88-92%, NOT 95%+ for COPD)
   - **First 14 days ONLY**: Twice daily temperature (pneumonia relapse surveillance)
   - Inhaler technique video submission (week 2 - verify correct use)
9. Critical alerts:
   - SpO2 <88% (COPD-specific threshold)
   - CAT score ≥20 (high symptom burden → exacerbation risk)
   - Increased purulent sputum production (exacerbation sign)
   - **Comorbidity alert**: Fever >38°C in first 30 days (pneumonia relapse concern)
10. **Day 18 alert**: Patient reports increased dyspnea x 2 days, sputum now yellow (was clear), no fever. CAT score increased from 15 to 23.
    - **Assessment**: COPD exacerbation (Anthonisen criteria: ≥2 of dyspnea/sputum volume/sputum purulence)
    - **Intervention**: Activate exacerbation action plan (patient has rescue pack at home)
      - Start prednisone 40 mg PO daily x 5 days
      - Start azithromycin 500 mg daily x 3 days (purulent sputum suggests bacterial component)
      - Increase albuterol/ipratropium inhaler use
    - **Monitoring**: Daily check-ins x 3 days. Symptoms improved by day 3 → Exacerbation treated successfully at home, avoided hospitalization.
11. Completes 90-day monitoring with 1 exacerbation (treated at home) → Pulmonology follow-up for long-term management, pulmonary rehab referral (proven to reduce exacerbations).

**Key insight**: 90-day monitoring (vs 30 days for other diseases) captures high re-exacerbation window. Exacerbation action plan + home rescue pack enabled rapid treatment without ER visit. Recent pneumonia required temperature monitoring modification (not standard for COPD post-acute, but added due to comorbidity).

---

### Scenario 3: COVID Patient Transitioning from Acute Care with Diabetes Comorbidity

**Presentation**: 55M completed 4 days of acute COVID care (remdesivir IV course complete, weaned off 4L NC oxygen, now room air SpO2 94%). Type 2 diabetes (baseline A1c 8.5%), glucose elevated during acute phase due to dexamethasone (now discontinued). Transitioning to post-acute COVID monitoring.

**Decision Tree**:
1. Primary diagnosis: **COVID-19 post-acute** (day 10 of illness, transitioning from acute care)
2. Comorbidity: **Diabetes** (worsened by dexamethasone during acute phase)
3. **Transition from acute care**: Patient completed COVID acute pathway (IV remdesivir finished, weaned off O2)
4. **Use [`references/covid-postacute.md`](references/covid-postacute.md)**, consult [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md) → COVID + Diabetes section
5. Monitoring duration: **14 days total from diagnosis** (10 days elapsed in acute care, remaining 4 days in post-acute)
   - **HOWEVER**: Given this is day 10 (peak severity window days 8-12), **extend post-acute monitoring to full 14 days from TODAY** (day 10) = 24 days total monitoring
6. Deploy: Everion armband (continue from acute care), thermometer, **ADD glucometer** (diabetes monitoring)
7. **Comorbidity modification**:
   - **Glucose monitoring**: QID glucose checks (fasting, pre-lunch, pre-dinner, bedtime) for first 7 days (dexamethasone effect lingers 5-7 days after discontinuation)
   - Alert threshold: Glucose >250 mg/dL (diabetes worsens COVID outcomes, tight control during recovery)
   - If glucose >250 mg/dL → Check ketones (DKA risk in setting of infection + recent corticosteroids)
   - Monitor for hyperglycemia relapse as dexamethasone effect wears off (may need insulin dose REDUCTION to avoid hypoglycemia)
8. Daily patient tasks:
   - Twice daily temperature (COVID standard)
   - Daily COVID questionnaire (Section A: 911 criteria, Section B: respiratory, Section C: systemic)
   - SpO2 monitoring (Everion continuous + spot checks - silent hypoxemia risk)
   - **QID glucose checks** (diabetes comorbidity addition)
   - Insulin dose logging
9. Critical alerts:
   - SpO2 <92% (COVID decompensation)
   - Emergency symptoms (chest pain, confusion, severe dyspnea) → 911
   - RR >25/min
   - **Comorbidity alerts**: Glucose <70 or >250 mg/dL
10. **Day 14 (of post-acute phase)**: Patient feeling much better, SpO2 98% on room air, afebrile x 5 days. **However**, reports persistent fatigue, "brain fog," difficulty concentrating (new symptoms, not present during acute phase).
    - **Assessment**: Possible **long COVID** (symptoms emerging after acute phase resolved)
    - **Intervention**:
      - Complete 14-day COVID post-acute monitoring as planned (no acute issues)
      - **Screen for long COVID** (symptoms >4 weeks from initial infection = long COVID by CDC definition)
      - Schedule PCP follow-up in 2 weeks
      - **If symptoms persist at 4 weeks post-infection** → Refer to multidisciplinary long COVID clinic (cardiology, pulmonology, neurology, rehab medicine)
11. Completes 14-day post-acute monitoring → Discharge to PCP. Long COVID screening scheduled at 4 weeks (currently 24 days post-infection).

**Key insight**: Post-acute COVID monitoring is **14 days** (shorter than most pathways because acute viral illness, not chronic disease). BUT patient was already on day 10 when transitioning from acute care → Need to extend post-acute monitoring to capture critical deterioration window (days 5-10 peak risk, but complications can occur through day 14). Diabetes comorbidity required glucose monitoring addition (not standard for COVID post-acute). Long COVID screening MANDATORY at completion (20-30% develop persistent symptoms).

---

## Frequently Asked Questions

**Q: How do I choose between acute and post-acute pathways?**  
A: **Post-acute = oral therapy + readmission prevention**. Acute = IV therapy + intensive monitoring. If patient is post-discharge (within 30-90 days) and on oral medications only, use post-acute pathway.

**Q: Patient discharged from outside hospital (not our acute care program). Can I still use post-acute pathway?**  
A: Yes. Post-acute pathways designed for ANY patient discharged with eligible diagnosis, regardless of where acute care occurred. Obtain discharge summary to understand acute care course, medication changes, complications.

**Q: What if patient has multiple diagnoses (e.g., discharged for CHF but also has COPD, diabetes, HTN)?**  
A: Select pathway based on **PRIMARY DISCHARGE DIAGNOSIS** (reason for hospitalization). Then consult comorbidity matrix for cross-disease modifications. Example: CHF discharge (primary) with COPD, diabetes, HTN (comorbidities) → Use CHF post-acute pathway, reference comorbidity matrix for each comorbidity.

**Q: Patient completed 30-day CHF post-acute monitoring but readmitted 2 weeks later for new CHF exacerbation. Start over?**  
A: Yes. Each new acute event (hospitalization or acute care pathway) triggers a NEW post-acute monitoring period. So patient would do ANOTHER 30 days of post-acute CHF monitoring starting from new discharge date.

**Q: How often should care team review patient data in post-acute care?**  
A: **Routine review q2-3 days** (vs daily in acute care). HOWEVER, critical alerts trigger immediate review (within 1 hour), urgent alerts within 24 hours. So actual review frequency depends on patient stability.

**Q: Can patient wear Everion armband continuously for 30-90 days? Battery life?**  
A: Everion designed for longer-term wear (charge nightly, wear ~22 hrs/day). VitalPatch used in acute care is 5-day disposable. For patients who find continuous wear burdensome, can do scheduled wearing times (e.g., daytime only, remove at night) + spot checks with pulse ox/BP cuff.

**Q: Patient non-compliant with daily tasks (missing questionnaires, not checking weight). What to do?**  
A: **Non-compliance is early warning sign**. Outreach to patient to identify barriers:
- Health literacy (doesn't understand importance) → Education
- Technical issues (app not working, device malfunction) → Troubleshooting
- Social factors (too busy, depressed, financially stressed) → Care coordination, social work referral
- Worsening symptoms (too sick to complete tasks) → Urgent clinical evaluation

**Q: When can patient stop using devices after completing post-acute monitoring?**  
A: **At program completion** (30/90/14 days), devices typically returned UNLESS patient wants to continue for ongoing self-monitoring. Some practices allow patients to keep weight scale (CHF), BP cuff (HTN), glucometer (diabetes) for long-term use. Everion armband usually returned (expensive, reusable).

---

## Updates & Maintenance

**Current Version**: 1.0  
**Last Updated**: 2026-02-01  
**Next Review**: Quarterly (or as new evidence-based guidelines published)

**Changelog**:
- 2026-02-01: Initial release with 7 post-acute disease pathways

---

## References

**Primary Source Document**: Carepath-Prod.pdf (Post-Acute Care Pathways for all 7 diseases)

**Clinical Guidelines**:
- ACC/AHA Heart Failure Guidelines 2022
- GOLD COPD Guidelines 2023
- IDSA/ATS Community-Acquired Pneumonia Guidelines
- AHA/ACC Hypertension Guidelines 2017
- ADA Standards of Diabetes Care 2024
- ACCP Antithrombotic Therapy Guidelines
- NIH COVID-19 Treatment Guidelines (updated regularly)
- CDC Long COVID Guidelines

**Evidence Base**:
- Remote patient monitoring reduces 30-day readmissions by 20-40% (NEJM 2021)
- Daily weights most predictive of CHF readmission (Circulation 2020)
- Early exacerbation treatment reduces COPD hospitalizations by 50% (Lancet Respir Med 2019)

**Device Manufacturers**:
- Biofourmis (Everion armband)
- Welch Allyn (scales, BP cuffs)
- Nonin Medical (pulse oximeters)
- Dexcom, Abbott (CGMs)

---

**For acute care (hospital-at-home IV therapy)**, see companion skill: [`carepath-acute`](../carepath-acute/SKILL.md)

**For transition protocols between acute and post-acute**, see: 
- [`references/transition-from-acute.md`](references/transition-from-acute.md) (acute → post-acute step-down)
- [`carepath-acute/references/transition-to-postacute.md`](../carepath-acute/references/transition-to-postacute.md) (acute care completion criteria)
