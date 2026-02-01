# CHF (Congestive Heart Failure) - Post-Acute Care Pathway

## Objective
Reduce risk of hospital readmission, ER visits, and premature mortality in CHF patients while optimizing patient comfort. Program targets patients transitioning to home after a hospital stay for acute treatment of CHF.

## Duration
**30 days** post-discharge

---

## Eligibility Criteria

### Inclusion
- Age 21-75
- Patient diagnosed with CHF, eligible for discharge and outpatient monitoring
- **Improving congestion**, off supplemental O2, transitioning to oral diuretics
- Ability to complete tasks and questionnaires in-app and use required devices

### Exclusion Criteria
- **Class IV / Stage D heart failure**
- **LVAD** (left ventricular assist device)
- **Inotropic or vasopressor support**
- **Severe pulmonary hypertension**
- **Hypotension** (unable to tolerate guideline-directed medical therapy)

---

## Primary Outcome Measures

| Outcome | Timeframe | Target |
|---------|-----------|--------|
| **30-Day Hospital Readmission** | 30 days | <20% (national ~25%) |
| **30-Day Mortality** | 30 days | <5% |
| **90-Day Mortality** | 90 days | <10% |
| **6-Month Mortality** | 6 months | <15% |
| **GDMT Adherence** | Ongoing | >80% medication adherence |
| **Medication Adherence** | Throughout | Daily tracking |
| **Patient Satisfaction** | End of program | >85% satisfaction |

---

## Devices & Monitoring Equipment

See **[Devices Reference](../../shared/devices.md)** for complete specifications.

### Required Devices
- **Everion Armband**
  - Continuous HR, RR, SpO2, skin temperature, activity levels
  - Lighter than VitalPatch used in acute care
- **Connected Weight Scale** (Welch Allyn RPM-SCALE100 OR ForaCare W550)
  - **CRITICAL**: Daily weight is #1 CHF monitoring parameter
- **Connected BP Cuff** (Welch Allyn 1700)

---

## Daily Monitoring Protocol & Tasks

### Daily Tasks (Patient-Performed)
1. **Twice Daily Weight**
   - Same time each day (morning preferred, after urination, before eating)
   - Same scale, same clothing
   - Record and transmit to care team
   
2. **Twice Daily BP Measurements**
   - Morning and evening
   - Seated, arm at heart level, 5 min rest before measurement

3. **Daily Fluid and Salt Intake Tracking**
   - Fluid restriction: Typically 1.5-2L/day
   - Sodium restriction: <2000mg/day (<1500mg if severe CHF)

4. **Medication Adherence Tracking**
   - GDMT medications (ACE-I/ARB, beta-blocker, diuretic, MRA)
   - Record taken/missed doses

### Clinical Team Monitoring (Daily Review)
- **Daily Biofourmis HF Symptom Checker**: See **[CHF Questionnaire - Daily Checker](../../shared/questionnaires/chf-questionnaire.md#1-daily-heart-failure-symptom-checker)**
  - Dyspnea assessment (with activity, at rest, lying down)
  - Chest pain, dizziness, functional status
  - Orthopnea, paroxysmal nocturnal dyspnea
  - Peripheral edema assessment

- **Monthly KCCQ-12**: See **[CHF Questionnaire - KCCQ-12](../../shared/questionnaires/chf-questionnaire.md#2-kccq-12-kansas-city-cardiomyopathy-questionnaire)**
  - Administer Day 0 and Day 30
  - Track score changes (≥5 point change is clinically meaningful)
  - Score <50 indicates high readmission risk

- **Optional PHQ-9** (at program initiation): Depression screening

---

## Alert Thresholds & Escalations

See **[Universal Alert Thresholds](../../shared/alert-thresholds.md)** for complete table and **[CHF Comorbidities](../../shared/comorbidity-matrix.md#chf--diabetes)** for interaction guidance.

### CHF-Specific Post-Acute Alerts

| Parameter | Threshold | Action |
|-----------|-----------|--------|
| **Weight Gain** | >0.9 kg/day OR >2.3 kg/week | **Same-day call**: Increase diuretic dose, assess fluid/salt intake |
| **SpO2** | <92% | **Urgent**: Assess for worsening CHF vs pneumonia, consider acute care transition |
| **Systolic BP** | <90 mmHg | **Hold ACE-I/diuretic**, assess volume status, clinical call |
| **Worsening Dyspnea** | New orthopnea or PND | **Same-day evaluation**: Assess for CHF exacerbation |
| **KCCQ-12 Score Drop** | ≥10 points from baseline | **Clinical evaluation**: Medication optimization needed |

### Comorbidity Monitoring
- **Diabetes**: Monitor glucose (diuretics worsen hyperglycemia)
- **HTN**: Ensure BP controlled (<130/80 with CHF)
- **COPD**: Differentiate dyspnea source (crackles=CHF, wheezes=COPD)

---

## Complications & Adverse Events to Monitor

### Volume Overload
- **Signs**: Shortness of breath with activity or lying down, persistent cough, swelling, rapid weight gain
- **Management**: Increase diuretics, fluid/salt restriction reinforcement

### Rapid or Irregular Heart Beat
- **Concern**: Atrial fibrillation with RVR (common CHF comorbidity)
- **Management**: Rate control, anticoagulation if new AFib

### Myocardial Infarction / Chest Pain
- **Concern**: ACS precipitates CHF exacerbation
- **Management**: **Emergency evaluation** if chest pain - ECG, troponin

### Progressive Kidney Damage and Renal Failure
- **Concern**: Cardiorenal syndrome
- **Management**: Monitor BMP, adjust diuretics/ACE-I doses, nephrology referral if worsening

### Uncontrolled Medical Comorbidities
- See **[Comorbidity Matrix](../../shared/comorbidity-matrix.md)** for CHF combinations

---

## Guideline-Directed Medical Therapy (GDMT)

### Core CHF Medications (All Patients Unless Contraindicated)

#### ACE Inhibitors or ARBs
- **Examples**: Lisinopril, enalapril (ACE-I); Losartan, valsartan (ARB)
- **Goal**: Reduce mortality, slow progression
- **Monitoring**: BMP (Cr, K), BP, cough (ACE-I side effect)

#### Beta-Blockers
- **Examples**: Carvedilol, metoprolol succinate, bisoprolol
- **Goal**: Reduce mortality, improve symptoms
- **Monitoring**: HR (target 60-70 bpm), BP, fatigue

#### Diuretics (Loop)
- **Examples**: Furosemide, bumetanide, torsemide
- **Goal**: Volume control, symptom relief
- **Monitoring**: Daily weight, BMP (K, Cr), BP

#### Mineralocorticoid Receptor Antagonists (MRA)
- **Examples**: Spironolactone, eplerenone
- **Goal**: Reduce mortality, hospitalization
- **Monitoring**: BMP (K - risk of hyperkalemia), gynecomastia (spironolactone)

### Optional/Add-On GDMT

#### SGLT2 Inhibitors
- **Examples**: Empagliflozin, dapagliflozin
- **Goal**: Reduce CHF hospitalizations (even in non-diabetics)
- **Benefit**: Dual benefit if patient also has diabetes

#### ARNI (Angiotensin Receptor-Neprilysin Inhibitor)
- **Example**: Sacubitril/valsartan (Entresto)
- **Goal**: Superior to ACE-I/ARB for reducing mortality and hospitalization
- **Note**: DO NOT combine with ACE-I (use instead of ACE-I/ARB)

#### Ivabradine
- **Goal**: Reduce HR if still elevated (>70) despite beta-blocker
- **Indication**: NSR (not for AFib), EF <35%, HR >70

### GDMT Adherence Tracking
- Daily medication tracking in app
- Pill counts at virtual visits
- **Goal**: >80% adherence
- **Barriers**: Cost, side effects, complexity - address proactively

---

## Patient Education Content

### CHF Education Topics (Via Patient App)
- What is heart failure? (pathophysiology in lay terms)
- Why daily weights matter
- Fluid and sodium restriction rationale and practical tips
- Medication importance and side effects
- When to call your care team (warning signs)
- Physical activity guidelines (gradual increase, monitor symptoms)

---

## Care Coordination & Escalation

### Daily Care Team Monitoring
- **Patient questionnaire responses**: Review daily symptom checker
- **Care plan adherence**: Weight recorded? BP recorded? Meds taken?
- **Alerts and physiologic parameters**: Weight trends, BP trends, activity levels

### Support and Intervention
- **Chat/Video**: Address questions, medication education, symptom assessment
- **Escalation**: Same-day clinical calls for alerts, urgent evaluation for severe symptoms

### Transition Back to Acute Care
**Criteria for Re-escalation**: See **[Transition from Post-Acute](./transition-from-acute.md)**
- Rapid weight gain (>2kg in 3 days) despite diuretic increase
- Worsening dyspnea requiring O2
- Hypotension precluding GDMT
- Chest pain/ACS
- **Action**: Transition back to `carepath-acute` skill for intensive management

---

## Other Recommended Care

### Follow-Up Appointments
- **Cardiology**: Within 7-14 days post-discharge
- **PCP**: Within 30 days
- **Dietician**: Sodium restriction counseling, meal planning

### Labs
- **BMP**: Week 1, Week 2, Week 4 (monitor K, Cr with GDMT titration)
- **BNP/NT-proBNP**: Optional - trend to assess treatment response

### Optional In-Home Services
- **ECG**: As needed per clinician recommendation (arrhythmia concern)
- **Echocardiogram**: Reassess EF at 3-6 months if on optimal GDMT

---

## Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **No 30-day readmission** | Primary goal | Track hospital admissions |
| **Weight stable** | ±0.5kg from dry weight | Daily weight tracking |
| **KCCQ-12 improvement** | ≥5 point increase | Compare Day 0 vs Day 30 |
| **GDMT adherence** | >80% | Daily medication tracking |
| **BP control** | SBP <130 mmHg | Twice daily measurements |

---

## References
- Source: Carepath CHF Post-Acute Care Pathway SOP
- ACC/AHA Heart Failure Guidelines 2022
- KCCQ-12 Scoring: cv-outcomes.org
- GDMT: Guideline-Directed Medical Therapy per ACC/AHA

**Related Skills**: If patient deteriorates, transition back to `carepath-acute` skill for intensive hospital-at-home management.
