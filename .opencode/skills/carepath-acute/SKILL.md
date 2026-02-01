---
name: carepath-acute
description: |
  Clinical decision support for acute remote patient monitoring across 7 disease pathways (CHF, COPD, Pneumonia, HTN, Diabetes, DVT, COVID-19).
  
  **Triggers**: "acute care", "IV diuresis", "exacerbation", "acute decompensation", "hospital at home", "O2 requirement", "IV antibiotics", "IV anticoagulation", "acute hyperglycemia", "DKA", "respiratory distress", "acute illness monitoring"
  
  Provides protocol guidance for hospital-at-home acute care including device selection, monitoring thresholds, alert escalation, daily care tasks, and complication management.
---

# Carepath Acute Care Pathways

**Version**: 1.0  
**Optimized for**: Qwen-Pro API + OpenCode  
**Coverage**: 7 acute disease pathways

---

## Quick Reference: Disease Selection

Use this table to quickly identify which acute care pathway to reference based on patient presentation:

| Disease | Acute Care Indication | Duration | Key Devices | Critical Alert Threshold |
|---------|----------------------|----------|-------------|--------------------------|
| **[CHF](references/chf-acute.md)** | IV diuresis for exacerbation | 2-10 days | Weight scale, BP cuff, VitalPatch, pulse ox | Weight gain ≥2 lbs/day or ≥5 lbs/week; SpO2 <92% |
| **[COPD](references/copd-acute.md)** | Acute exacerbation (AECOPD) requiring IV/oral corticosteroids | 3-7 days | VitalPatch, pulse ox, BP cuff, spirometer | SpO2 <88%; RR >28/min; Severe dyspnea (CAT ≥30) |
| **[Pneumonia](references/pneumonia-acute.md)** | Community-acquired pneumonia (CAP) requiring IV antibiotics | 5-10 days | VitalPatch, pulse ox, thermometer | Temp >39°C; SpO2 <92%; RR >25/min; HR >110 bpm |
| **[HTN](references/htn-acute.md)** | Severe HTN requiring IV antihypertensives (not hypertensive emergency) | 1-3 days | BP cuff, VitalPatch | SBP >180 or DBP >110 mmHg; SBP drop >40 mmHg/hr |
| **[Diabetes](references/diabetes-acute.md)** | DKA or HHS requiring IV insulin + fluids | 2-5 days | CGM, glucometer, ketone meter, VitalPatch | Glucose <70 or >300 mg/dL; Ketones ≥1.5 mmol/L; Altered mental status |
| **[DVT](references/dvt-acute.md)** | Acute DVT requiring IV anticoagulation (heparin → transition to oral) | 3-7 days | Doppler-capable device, VitalPatch, pulse ox | New chest pain/dyspnea (PE); Severe leg swelling; Bleeding (anticoagulation complication) |
| **[COVID-19](references/covid-acute.md)** | COVID pneumonia requiring IV antivirals, monitoring, or O2 support | 2-6 days | Everion armband, pulse ox, thermometer | SpO2 <92%; RR >25/min; Confusion; Chest pain (emergency symptoms) |

---

## When to Use This Skill

### Acute Care Pathway Criteria (vs Post-Acute)

**Use `carepath-acute` skill when patient requires**:

1. **IV therapy**:
   - IV diuretics (CHF)
   - IV corticosteroids (COPD)
   - IV antibiotics (Pneumonia)
   - IV antihypertensives (HTN)
   - IV insulin (Diabetes DKA/HHS)
   - IV anticoagulation (DVT - initial heparin phase)
   - IV antivirals or monoclonal antibodies (COVID-19)

2. **Intensive monitoring** (hospital-at-home level):
   - Continuous vital sign telemetry required
   - Daily clinical team assessment needed
   - High risk of rapid deterioration
   - Needs coordination of phlebotomy, radiology, medication administration

3. **Acute decompensation**:
   - CHF exacerbation with fluid overload
   - COPD acute exacerbation (AECOPD)
   - Acute respiratory infection requiring IV treatment
   - Hypertensive urgency (not emergency - emergency requires ICU)
   - DKA or HHS
   - Acute thrombotic event
   - COVID pneumonia with oxygen requirement

**Do NOT use for**:
- Post-discharge readmission prevention → Use `carepath-postacute` skill instead
- Stable chronic disease management → Primary care
- Hypertensive emergency (encephalopathy, stroke, MI) → ICU/ED
- Critically ill patients (vasopressors, mechanical ventilation, altered mental status) → ICU

---

## How to Use This Skill

### Step 1: Identify Disease Pathway

Match patient's primary acute condition to one of 7 pathways using Quick Reference table above.

**For patients with multiple comorbidities**:
- Select pathway based on PRIMARY ACUTE ILLNESS requiring treatment
- Example: Patient with CHF + COPD admitted for CHF exacerbation → Use **CHF acute pathway**, reference COPD comorbidity considerations within that protocol
- See [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md) for cross-disease interactions

### Step 2: Verify Eligibility

Open disease-specific acute pathway reference and confirm:
- Patient meets **inclusion criteria**
- Patient does NOT meet any **exclusion criteria** (exclusions typically indicate ICU-level care needed)

### Step 3: Protocol Implementation

Each acute pathway reference provides structured sections:

1. **Devices & Monitoring Equipment**: Which connected devices to deploy
2. **Daily Monitoring Tasks**: Care team review checklist
3. **Alerts/Thresholds/Escalations**: When to escalate (see also universal thresholds below)
4. **Treatment Protocol**: Medication administration, IV therapy, titration guidelines
5. **Complications**: What to watch for and how to manage
6. **Comorbidity Considerations**: How co-existing diseases modify the protocol
7. **Transition Criteria**: When patient is stable enough for step-down to post-acute care

### Step 4: Alert Management

**Universal alert thresholds** are documented in [`shared/alert-thresholds.md`](../shared/alert-thresholds.md).

**Disease-specific threshold modifications** are in each pathway reference (e.g., COPD patients tolerate lower SpO2 baseline).

**Escalation levels**:
- 🔴 **CRITICAL (Red)**: Immediate response required (<5 min) - life-threatening
- 🟠 **URGENT (Orange)**: Response within 1 hour - high risk of decompensation
- 🟡 **ADVISORY (Yellow)**: Response within 4 hours - trending concern

### Step 5: Questionnaires & Symptom Monitoring

Daily patient-reported symptom questionnaires are in [`shared/questionnaires/`](../shared/questionnaires/):

- [`chf-questionnaire.md`](../shared/questionnaires/chf-questionnaire.md) - Daily fluid status + KCCQ-12
- [`copd-questionnaire.md`](../shared/questionnaires/copd-questionnaire.md) - Daily exacerbation symptoms + CAT score
- [`pneumonia-questionnaire.md`](../shared/questionnaires/pneumonia-questionnaire.md) - Infection symptoms, CURB-65 elements
- [`htn-questionnaire.md`](../shared/questionnaires/htn-questionnaire.md) - Hypertensive emergency symptoms
- [`diabetes-questionnaire.md`](../shared/questionnaires/diabetes-questionnaire.md) - Hypo/hyperglycemia assessment
- [`dvt-questionnaire.md`](../shared/questionnaires/dvt-questionnaire.md) - PE warning signs + anticoagulation safety
- [`covid-questionnaire.md`](../shared/questionnaires/covid-questionnaire.md) - 911 criteria + respiratory/systemic symptoms

Each questionnaire includes:
- Questions with response options
- Scoring/interpretation guidelines
- Clinical decision rules (when to escalate)

---

## Disease Pathway References

### 1. CHF (Congestive Heart Failure) Acute Care

**File**: [`references/chf-acute.md`](references/chf-acute.md)

**Objective**: Enable hospital-at-home IV diuresis for CHF exacerbation with physiologic monitoring and care coordination.

**Duration**: 2-10 days (typical 3-7 days)

**Eligibility**:
- Clinical/diagnostic evidence of CHF exacerbation requiring IV diuresis
- ✗ Exclusions: GWTG-HF risk >10%, Stage D, LVAD, inotropes, severe PH, O2 >4L NC

**Key Devices**:
- **Weight scale** (daily weight = #1 CHF monitor)
- BP cuff, pulse oximeter, VitalPatch (continuous telemetry - optional)

**Critical Alerts**:
- Weight gain ≥2 lbs/day or ≥5 lbs/week
- SpO2 <92%
- Worsening orthopnea, PND, edema

**Treatment**:
- IV loop diuretics (furosemide, bumetanide, torsemide)
- Daily electrolyte monitoring (K+, Na+, Cr, BUN)
- GDMT optimization (ACEi/ARB/ARNI, beta-blocker, MRA, SGLT2i)

**Complications**: Cardiorenal syndrome, electrolyte abnormalities, worsening renal function, diuretic resistance

**Transition to Post-Acute**: When euvolemic (stable weight, resolved orthopnea/edema), IV diuretics converted to oral, electrolytes stable

---

### 2. COPD Acute Care

**File**: [`references/copd-acute.md`](references/copd-acute.md)

**Objective**: Treat acute COPD exacerbation (AECOPD) with corticosteroids, bronchodilators, antibiotics (if indicated), and oxygen therapy in hospital-at-home setting.

**Duration**: 3-7 days

**Eligibility**:
- Acute worsening of dyspnea, cough, sputum production beyond baseline
- ✗ Exclusions: Respiratory failure (PCO2 >60 mmHg), O2 >6L NC, altered mental status

**Key Devices**:
- VitalPatch (continuous HR, RR, SpO2), pulse oximeter, BP cuff, spirometer (optional)

**Critical Alerts**:
- SpO2 <88% (COPD target 88-92%, not 95%+)
- RR >28/min
- Severe dyspnea (CAT score ≥30)

**Treatment**:
- Systemic corticosteroids (prednisone 40 mg x 5 days or IV methylprednisolone)
- Bronchodilators (albuterol/ipratropium nebulizers or MDI)
- Antibiotics if purulent sputum (azithromycin, doxycycline, amoxicillin-clavulanate)
- Oxygen therapy (target SpO2 88-92%)

**Complications**: Respiratory failure, pneumonia, PE, pneumothorax, cardiac arrhythmias (from beta-agonists)

**Transition to Post-Acute**: Symptom improvement, oxygen weaned to baseline or <4L NC, stable vitals

---

### 3. Pneumonia Acute Care

**File**: [`references/pneumonia-acute.md`](references/pneumonia-acute.md)

**Objective**: Treat community-acquired pneumonia (CAP) requiring IV antibiotics with physiologic monitoring and supportive care in hospital-at-home setting.

**Duration**: 5-10 days

**Eligibility**:
- CAP confirmed or suspected (infiltrate on CXR/CT, clinical presentation)
- PSI (Pneumonia Severity Index) Class III-IV, or CURB-65 score 1-2
- ✗ Exclusions: ICU criteria (septic shock, mechanical ventilation), severe hypoxemia (SpO2 <90% on 6L NC)

**Key Devices**:
- VitalPatch (continuous telemetry), pulse oximeter, thermometer, BP cuff

**Critical Alerts**:
- Temperature >39°C or <36°C (sepsis concern)
- SpO2 <92%
- RR >25/min or HR >110 bpm
- Confusion (altered mental status)

**Treatment**:
- IV antibiotics (ceftriaxone + azithromycin OR fluoroquinolone)
- Oxygen therapy if SpO2 <94%
- Antipyretics for comfort
- IV fluids if dehydrated

**Complications**: Pleural effusion/empyema, lung abscess, sepsis, ARDS, multi-organ failure

**Transition to Post-Acute**: Fever resolved (afebrile >24 hrs), SpO2 stable, switched to oral antibiotics, vital signs normalizing

---

### 4. HTN (Hypertension) Acute Care

**File**: [`references/htn-acute.md`](references/htn-acute.md)

**Objective**: Treat **hypertensive urgency** (severe HTN without end-organ damage) requiring IV antihypertensives with close BP monitoring in hospital-at-home setting.

**Duration**: 1-3 days (shortest acute pathway - rapid BP control)

**Eligibility**:
- SBP ≥180 mmHg or DBP ≥110 mmHg WITHOUT end-organ damage symptoms
- ✗ Exclusions: **Hypertensive emergency** (encephalopathy, stroke, MI, acute CHF, aortic dissection, AKI) → requires ICU

**Key Devices**:
- BP cuff (every 2-4 hours initially), VitalPatch (continuous HR monitoring)

**Critical Alerts**:
- SBP >180 mmHg or DBP >110 mmHg (sustained after treatment)
- SBP drop >40 mmHg/hr (too rapid, risk of hypoperfusion)
- Symptoms of end-organ damage (headache, chest pain, vision changes, confusion)

**Treatment**:
- IV antihypertensives (labetalol, nicardipine, hydralazine) - initial rapid control
- Transition to oral agents (ACEi/ARB, CCB, diuretic, beta-blocker)
- Goal: Reduce BP by 25% in first 1-2 hours, then gradually to <160/100 over 24-48 hrs

**Complications**: Stroke (hemorrhagic or ischemic), MI, acute CHF, hypertensive encephalopathy, AKI

**Transition to Post-Acute**: BP controlled <160/100 mmHg on oral meds, no symptoms of end-organ damage

---

### 5. Diabetes Acute Care

**File**: [`references/diabetes-acute.md`](references/diabetes-acute.md)

**Objective**: Treat DKA (diabetic ketoacidosis) or HHS (hyperosmolar hyperglycemic state) requiring IV insulin and fluids in hospital-at-home setting.

**Duration**: 2-5 days

**Eligibility**:
- **DKA**: Glucose >250 mg/dL, ketones ≥1.5 mmol/L, pH <7.3, anion gap >10
- **HHS**: Glucose >600 mg/dL, serum osmolality >320 mOsm/kg, minimal ketones
- ✗ Exclusions: Severe DKA (pH <7.0), altered mental status (GCS <13), severe electrolyte abnormalities, pediatric DKA

**Key Devices**:
- CGM (continuous glucose monitor) or frequent glucometer checks (q1hr initially)
- Ketone meter (blood or urine)
- VitalPatch (HR, RR monitoring)

**Critical Alerts**:
- Glucose <70 mg/dL (hypoglycemia)
- Glucose >300 mg/dL with rising ketones (inadequate insulin)
- Ketones ≥1.5 mmol/L (persistent/worsening DKA)
- Altered mental status (cerebral edema, severe hypoglycemia)

**Treatment**:
- **DKA Protocol**: IV insulin infusion (0.1 unit/kg/hr), IV fluids (NS then 0.45% NaCl), potassium replacement
- **HHS Protocol**: IV fluids (aggressive - 1-2L/hr initially), IV insulin (lower dose than DKA)
- Transition to subcutaneous insulin when gap closed (DKA) or glucose <300 mg/dL (HHS)

**Complications**: Cerebral edema (rare in adults), hypokalemia, hypoglycemia, rebound hyperglycemia

**Transition to Post-Acute**: DKA resolved (glucose <200 mg/dL, pH >7.3, anion gap <12) or HHS resolved (glucose <250 mg/dL, mental status normal), on stable subcutaneous insulin regimen

---

### 6. DVT (Deep Vein Thrombosis) Acute Care

**File**: [`references/dvt-acute.md`](references/dvt-acute.md)

**Objective**: Treat acute DVT with IV anticoagulation (heparin/LMWH) and transition to oral anticoagulant in hospital-at-home setting.

**Duration**: 3-7 days (initial parenteral anticoagulation phase)

**Eligibility**:
- Acute DVT confirmed by Doppler ultrasound
- Low-intermediate PE risk (if PE suspected, evaluate with CTPA)
- ✗ Exclusions: High-risk PE (massive PE, hemodynamic instability), active bleeding, severe renal failure (Cr >2.5)

**Key Devices**:
- Doppler-capable device (for serial leg assessments - optional)
- VitalPatch (HR, RR, SpO2 monitoring for PE detection)
- Pulse oximeter

**Critical Alerts**:
- New chest pain, dyspnea, tachycardia (PE symptoms)
- Severe leg swelling or discoloration (phlegmasia cerulea dolens - limb-threatening)
- Bleeding (anticoagulation complication - GI bleed, hematuria, intracranial hemorrhage)

**Treatment**:
- **Parenteral anticoagulation**: Unfractionated heparin IV (bolus + infusion, monitor aPTT) OR LMWH subcutaneous (enoxaparin 1 mg/kg q12hr)
- **Transition to oral anticoagulant**: Warfarin (overlap 5 days until INR 2-3) OR DOAC (rivaroxaban, apixaban) - can start day 1 with some DOACs
- Duration: Minimum 3 months, possibly lifelong if unprovoked or recurrent

**Complications**: PE, phlegmasia (limb-threatening DVT), post-thrombotic syndrome, bleeding (anticoagulation)

**Transition to Post-Acute**: Stable on oral anticoagulation, therapeutic INR (if warfarin) or completed loading dose (if DOAC), no bleeding, no PE

---

### 7. COVID-19 Acute Care

**File**: [`references/covid-acute.md`](references/covid-acute.md)

**Objective**: Treat COVID-19 pneumonia requiring IV antivirals, supplemental oxygen, or close monitoring in hospital-at-home setting.

**Duration**: 2-6 days (shorter acute phase than bacterial infections)

**Eligibility**:
- Confirmed COVID-19 diagnosis (PCR or rapid antigen)
- Oxygen requirement ≤4L NC (SpO2 goal ≥92%)
- Moderate COVID severity (dyspnea, SpO2 <94% on room air)
- ✗ Exclusions: Severe hypoxemia (SpO2 <92% on 4L NC), respiratory failure, altered mental status, hemodynamic instability

**Key Devices**:
- Everion armband (continuous HR, RR, SpO2, skin temp, activity)
- Pulse oximeter (backup or for spot checks)
- Thermometer

**Critical Alerts**:
- SpO2 <92% (silent hypoxemia is common in COVID)
- RR >25/min
- Emergency symptoms (blue lips, chest pain, confusion, severe dyspnea) → 911
- Fever >40°C

**Treatment**:
- **Antiviral therapy**: Remdesivir IV (5-day course) if within 7 days of symptom onset
- **Corticosteroids**: Dexamethasone 6 mg PO/IV daily if oxygen requirement present
- **Oxygen therapy**: Target SpO2 ≥92%
- **Prone positioning**: Can improve oxygenation by 2-5% (educate patient)
- **Anticoagulation**: Prophylactic-dose (heparin 5000 units SQ q8-12hr or enoxaparin 40 mg daily) to prevent VTE

**Complications**: Progressive COVID pneumonia, ARDS, bacterial superinfection, VTE (DVT/PE), myocarditis, stroke

**Transition to Post-Acute**: Weaned off oxygen (or stable on <4L NC), fever resolved, symptom improvement, completed acute IV therapy → continue 14-day post-acute monitoring

---

## Shared Resources

All acute care pathways reference these shared knowledge bases:

### 1. Alert Thresholds & Escalation Protocols

**File**: [`shared/alert-thresholds.md`](../shared/alert-thresholds.md)

Universal vital sign thresholds for:
- SpO2, heart rate, respiratory rate, blood pressure, temperature
- 3-tier escalation (Critical/Urgent/Advisory)
- Disease-specific threshold modifications (e.g., COPD SpO2 target 88-92%)

### 2. Monitoring Devices Catalog

**File**: [`shared/devices.md`](../shared/devices.md)

Complete specifications for all connected devices:
- VitalConnect VitalPatch (continuous telemetry)
- Weight scales (Welch Allyn RPM-SCALE100, ForaCare W550)
- BP cuffs (Welch Allyn 1700, Omron BP7000)
- Pulse oximeters (Nonin 3230)
- Glucometers, CGMs, ketone meters
- Everion armband (COVID monitoring)

Includes: Device accuracy, setup instructions, troubleshooting, pathway applicability

### 3. Disease-Specific Questionnaires

**Directory**: [`shared/questionnaires/`](../shared/questionnaires/)

7 daily symptom questionnaires with scoring, interpretation, and clinical decision rules:
- CHF: Fluid status + KCCQ-12 quality of life
- COPD: Exacerbation symptoms + CAT score
- Pneumonia: Infection symptoms, CURB-65 elements
- HTN: Hypertensive emergency symptoms
- Diabetes: Hypo/hyperglycemia assessment
- DVT: PE warning signs + anticoagulation safety
- COVID: 911 criteria + respiratory/systemic symptoms

### 4. Comorbidity Interaction Matrix

**File**: [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md)

Cross-disease considerations for patients with multiple conditions:
- CHF + COPD: Dyspnea differentiation, BNP vs exacerbation
- CHF + HTN: BP targets, medication overlap
- Diabetes + COVID: Hyperglycemia worsens outcomes, DKA risk
- COPD + Pneumonia: Exacerbation vs infection
- DVT + COVID: Hypercoagulability, prophylactic anticoagulation
- And 25+ other combinations

---

## Transition to Post-Acute Care

**File**: [`references/transition-to-postacute.md`](references/transition-to-postacute.md)

When patient is stable enough to step down from acute care to post-acute monitoring:

### General Criteria (applies to all pathways):
1. **Clinical stability**: Vital signs normalizing, acute symptoms resolving
2. **Transitioned to oral therapy**: No longer requires IV medications
3. **Complication-free**: No active complications requiring intensive management
4. **Safe for lower-intensity monitoring**: No critical alerts in past 24-48 hours

### Disease-Specific Transition Criteria:

- **CHF**: Euvolemic (stable weight, resolved edema/orthopnea), on oral diuretics, electrolytes stable
- **COPD**: Symptom improvement, oxygen weaned to baseline or <4L NC, stable vitals
- **Pneumonia**: Afebrile >24 hrs, SpO2 stable, switched to oral antibiotics
- **HTN**: BP controlled <160/100 on oral meds, no end-organ damage symptoms
- **Diabetes**: DKA/HHS resolved, stable on subcutaneous insulin
- **DVT**: Stable on oral anticoagulation, no bleeding, no PE
- **COVID**: Weaned off oxygen (or stable <4L NC), fever resolved, symptom improvement

### Transition Process:
1. Confirm transition criteria met
2. Update medication list (IV → oral conversions)
3. Adjust device requirements (may discontinue VitalPatch, keep weight scale/BP cuff/etc.)
4. Lower alert threshold sensitivity (fewer critical alerts expected)
5. Transfer to post-acute care team with handoff note
6. Continue monitoring per post-acute pathway (30-90 days depending on disease)

**See also**: [`carepath-postacute` skill](../carepath-postacute/SKILL.md) for post-acute monitoring protocols

---

## Clinical Pearls

### Universal Acute Care Principles

1. **Continuous telemetry (VitalPatch) is OPTIONAL** - Use when high risk of sudden decompensation (severe CHF, pneumonia, COVID). Not required for HTN, stable diabetes, or low-risk DVT.

2. **Daily care team review is MANDATORY** - Acute care requires daily review of physiologic data, questionnaires, and task compliance (unlike post-acute which may be q2-3 days).

3. **IV therapy is the defining feature** - If patient no longer needs IV medications, consider transition to post-acute care.

4. **Escalation thresholds are TIGHTER in acute care** - Lower threshold for urgent intervention vs post-acute monitoring.

5. **Phlebotomy/imaging coordination** - Acute care includes coordination of labs (daily electrolytes for diuretics, aPTT for heparin, glucose for insulin) and imaging (CXR for pneumonia, Doppler for DVT).

6. **Family/caregiver involvement** - Acute care at home requires reliable support system for medication administration, monitoring assistance, emergency recognition.

### Red Flags Requiring ICU Transfer (NOT Hospital-at-Home)

**ANY of these → patient NOT suitable for acute care pathway, requires ICU**:

- **Respiratory**: SpO2 <90% on 6L NC, respiratory rate >30/min, use of accessory muscles, inability to speak full sentences
- **Hemodynamic**: SBP <90 mmHg, MAP <65 mmHg, requiring vasopressors (norepinephrine, vasopressin)
- **Neurological**: Altered mental status (GCS <13), confusion, disorientation, seizures
- **Renal**: Anuria, severe AKI requiring dialysis
- **Metabolic**: Severe acidosis (pH <7.1), severe electrolyte abnormalities (K+ >6.5 or <2.5 mmol/L)
- **Hematologic**: Active severe bleeding requiring transfusion, DIC
- **Social**: Unsafe home environment, no caregiver support, patient unable to cooperate with monitoring

**If patient develops any ICU criteria during acute care → immediate ED transfer**

---

## Example Usage Scenarios

### Scenario 1: CHF Patient with Acute Exacerbation

**Presentation**: 68F with known systolic CHF (EF 30%), presents with 5-day history of progressive dyspnea, orthopnea, and leg swelling. Weight up 8 lbs from baseline. SpO2 92% on room air.

**Decision Tree**:
1. Primary acute illness: **CHF exacerbation**
2. Check eligibility: Requires IV diuresis ✓, GWTG-HF risk <10% ✓, no LVAD ✓, SpO2 >90% on ≤4L NC ✓
3. **Use [`references/chf-acute.md`](references/chf-acute.md)**
4. Deploy: Weight scale, BP cuff, pulse oximeter, VitalPatch (optional - recommend given hypoxemia)
5. Treatment: IV furosemide 40 mg BID, daily electrolytes, daily CHF questionnaire
6. Critical alerts: Weight gain ≥2 lbs/day, SpO2 <92%, worsening orthopnea
7. Comorbidity check: None documented, but ask about COPD/pneumonia (dyspnea differential)
8. Monitor 3-7 days until euvolemic, then transition to post-acute CHF pathway

---

### Scenario 2: COPD Patient with AECOPD + Pneumonia (Comorbidity)

**Presentation**: 72M with severe COPD (FEV1 35% predicted), baseline O2 2L NC. Presents with 3-day history of worsening dyspnea, increased sputum production (now purulent), fever 38.8°C. CXR shows RLL infiltrate. SpO2 88% on 4L NC (up from baseline 2L).

**Decision Tree**:
1. Primary acute illness: **Pneumonia** (CXR infiltrate, fever, purulent sputum) + **COPD exacerbation** (comorbid)
2. Choose pathway: **Pneumonia is PRIMARY** (requires IV antibiotics + longer treatment course) → Use [`references/pneumonia-acute.md`](references/pneumonia-acute.md)
3. Check eligibility: CAP confirmed ✓, PSI Class III ✓, SpO2 >90% on 6L NC ✓
4. Deploy: VitalPatch, pulse oximeter, thermometer, BP cuff
5. Treatment:
   - **Pneumonia**: IV ceftriaxone 1g daily + azithromycin 500 mg daily (CAP protocol)
   - **COPD**: Add prednisone 40 mg PO daily x 5 days + albuterol/ipratropium nebs q4-6hr (AECOPD protocol)
   - **Oxygen**: Titrate to SpO2 88-92% (COPD target, NOT 95%+)
6. **Comorbidity modification**: Consult [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md) → COPD + Pneumonia section
   - Alert thresholds: SpO2 <88% (not <92%), RR >28/min
   - Differentiation: Purulent sputum + fever + CXR infiltrate = pneumonia (not just exacerbation)
   - Treatment: Add COPD exacerbation management to pneumonia protocol (corticosteroids, bronchodilators)
7. Monitor 5-10 days (pneumonia timeline), then transition to post-acute pneumonia pathway (which will also address ongoing COPD management)

---

### Scenario 3: COVID Patient with Diabetes Comorbidity

**Presentation**: 55M with type 2 diabetes (A1c 8.5%), COVID-19 positive (day 6 of symptoms). Dyspnea on exertion, SpO2 92% on room air. Glucose 320 mg/dL (poorly controlled at baseline). No ketones.

**Decision Tree**:
1. Primary acute illness: **COVID-19** (oxygen requirement, within treatment window)
2. Check eligibility: Confirmed COVID ✓, SpO2 ≥92% on ≤4L NC ✓ (borderline), stable symptoms ✓
3. **Use [`references/covid-acute.md`](references/covid-acute.md)**
4. Deploy: Everion armband, pulse oximeter, thermometer
5. Treatment:
   - **COVID**: Remdesivir IV (5-day course - within 7 days of symptom onset), dexamethasone 6 mg daily (oxygen requirement present)
   - **Diabetes**: ADD glucometer for QID glucose checks (dexamethasone will worsen hyperglycemia)
6. **Comorbidity modification**: Consult [`shared/comorbidity-matrix.md`](../shared/comorbidity-matrix.md) → COVID + Diabetes section
   - Alert thresholds: ADD glucose >300 mg/dL alert
   - Monitoring: Daily glucose checks (QID if on dexamethasone), ketone monitoring if glucose >250 mg/dL
   - Treatment: Increase insulin doses (dexamethasone causes significant hyperglycemia), target glucose <180 mg/dL
   - Risk: Diabetes worsens COVID outcomes → lower threshold for escalation if SpO2 declines
7. Monitor 2-6 days (acute COVID phase), then transition to post-acute COVID pathway (14 days) with continued diabetes monitoring

**Key insight**: Dexamethasone (indicated for COVID with oxygen requirement) will worsen diabetes → MUST add glucose monitoring to COVID protocol when this comorbidity exists.

---

## Frequently Asked Questions

**Q: How do I choose between acute and post-acute pathways?**  
A: **Acute care = IV therapy + intensive monitoring**. Post-acute care = oral therapy + readmission prevention. If patient requires IV medications (diuretics, antibiotics, insulin, anticoagulation), use acute care pathway. If patient is post-discharge and on oral meds, use post-acute pathway.

**Q: Patient has multiple diseases (e.g., CHF + COPD + diabetes). Which pathway do I use?**  
A: Select pathway based on **PRIMARY ACUTE ILLNESS** requiring treatment NOW. Then consult comorbidity matrix for cross-disease modifications. Example: CHF patient admitted for exacerbation (primary) who also has COPD (comorbidity) → Use CHF acute pathway, reference CHF+COPD comorbidity considerations.

**Q: What if patient deteriorates and needs ICU-level care?**  
A: Immediately transfer to ED/ICU. See "Red Flags Requiring ICU Transfer" section above. Hospital-at-home is NOT appropriate for: vasopressors, mechanical ventilation, altered mental status, SBP <90, SpO2 <90% on 6L NC.

**Q: How often should I review patient data in acute care vs post-acute care?**  
A: **Acute care = DAILY review** by clinical team (minimum). Post-acute care = q2-3 days review (unless alerts trigger earlier review).

**Q: Can I use multiple disease pathways simultaneously?**  
A: No. Select ONE primary pathway based on acute illness. Use comorbidity matrix to modify that pathway for co-existing diseases. Trying to follow 2+ pathways simultaneously creates conflicting monitoring frequencies and alert thresholds.

**Q: What devices are absolutely required vs optional?**  
A: See each disease pathway's "Devices" section. Generally:
- **Always required**: Disease-specific critical device (weight scale for CHF, pulse ox for respiratory diseases, glucometer for diabetes)
- **Recommended**: VitalPatch for high-risk patients (severe illness, high decompensation risk)
- **Optional**: Spirometer, Doppler, activity trackers

---

## Updates & Maintenance

**Current Version**: 1.0  
**Last Updated**: 2026-02-01  
**Next Review**: Quarterly (or as new evidence-based guidelines published)

**Changelog**:
- 2026-02-01: Initial release with 7 acute disease pathways

---

## References

**Primary Source Document**: Carepath-Prod.pdf (Acute Care Pathways for all 7 diseases)

**Clinical Guidelines**:
- ACC/AHA Heart Failure Guidelines 2022
- GOLD COPD Guidelines 2023
- IDSA/ATS Community-Acquired Pneumonia Guidelines
- AHA/ACC Hypertension Guidelines 2017
- ADA Standards of Diabetes Care 2024
- ACCP Antithrombotic Therapy Guidelines
- NIH COVID-19 Treatment Guidelines (updated regularly)

**Device Manufacturers**:
- VitalConnect (VitalPatch)
- Welch Allyn (scales, BP cuffs)
- Nonin Medical (pulse oximeters)
- Biofourmis (Everion armband)

---

**For post-acute care (discharge readmission prevention)**, see companion skill: [`carepath-postacute`](../carepath-postacute/SKILL.md)

**For transition protocols between acute and post-acute**, see: [`references/transition-to-postacute.md`](references/transition-to-postacute.md)
