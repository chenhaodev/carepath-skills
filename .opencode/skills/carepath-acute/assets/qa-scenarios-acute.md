# QA Scenarios - Carepath Acute Care Skill

**Purpose**: Manual verification scenarios for the `carepath-acute` skill covering all 7 disease pathways.

**Usage**: These scenarios test skill responses for typical clinical situations. Use synthetic data only - no real PHI.

---

## Scenario 1: CHF - New Patient Admission

### Patient Presentation
- **Patient**: 68-year-old male
- **Diagnosis**: CHF exacerbation with fluid overload
- **Symptoms**: Dyspnea, +2 pitting edema bilateral lower extremities, orthopnea (3-pillow)
- **Vital Signs**: BP 158/92, HR 98, RR 22, SpO2 94% on room air
- **Weight**: 92.3 kg (baseline 88.1 kg - gained 4.2 kg in 5 days)

### Question
"I need to set up hospital-at-home monitoring for this CHF patient. What devices and monitoring do I need?"

### Expected Response Elements
- [ ] **Duration**: 2-10 days (typical 3-7)
- [ ] **Devices**:
  - Weight scale (Welch Allyn RPM-SCALE100 or ForaCare W550) - **critical**
  - BP cuff (Welch Allyn 1700 or Omron BP7000)
  - Optional: VitalPatch for continuous telemetry, pulse oximeter
- [ ] **Daily monitoring**:
  - Daily weight (most important parameter)
  - BP measurements
  - CHF symptom questionnaire (KCCQ-12 monthly)
  - Fluid/salt intake tracking
- [ ] **Critical alert threshold**: Weight gain ≥0.9 kg/day or ≥2.3 kg/week
- [ ] **Reference to**: CHF acute pathway, CHF questionnaire, devices catalog

---

## Scenario 2: COPD - Alert Triage

### Patient Presentation
- **Patient**: 72-year-old female on day 4 of acute COPD exacerbation treatment
- **Current**: On oral corticosteroids, increased bronchodilator use
- **Device Alert**: SpO2 reading of 89% (down from baseline 92-93%)

### Question
"Patient's SpO2 dropped to 89%. Is this an emergency? What should I check?"

### Expected Response Elements
- [ ] **Alert level**: Depends on COPD baseline
  - If baseline SpO2 92-93%, this is a 3-4% drop → **urgent alert**
  - COPD patients often have lower baseline (88-92% acceptable)
- [ ] **What to check**:
  - Is patient using oxygen? What flow rate?
  - Any change in dyspnea, activity level, sputum production?
  - Check COPD daily questionnaire responses
  - CAT score trending up?
- [ ] **Critical threshold**: SpO2 <88% = critical alert
- [ ] **Actions**:
  - Review physiologic data trend
  - Virtual visit to assess respiratory status
  - Consider increasing oxygen if needed
- [ ] **Reference to**: COPD acute pathway, alert thresholds, COPD questionnaire

---

## Scenario 3: Pneumonia - Treatment Response

### Patient Presentation
- **Patient**: 54-year-old male, day 6 of IV ceftriaxone for CAP
- **Progress**: Initially improving (temp down, less dyspnea)
- **New symptom**: Temp spiked to 38.9°C this morning, increased cough

### Question
"Pneumonia patient was improving but now has fever again on day 6. What does this indicate?"

### Expected Response Elements
- [ ] **Fever threshold**: 38.9°C triggers urgent alert (threshold >38.5°C)
- [ ] **Differential**:
  - Treatment failure (resistant organism)
  - Complication (empyema, lung abscess)
  - New infection (C. diff from antibiotics)
  - Drug fever
- [ ] **Assessment needed**:
  - Review pneumonia daily questionnaire (mucus color, cough severity)
  - Check if patient took temperature correctly
  - Assess for GI symptoms (C. diff)
  - Review antibiotic adherence
- [ ] **Next steps**:
  - Urgent physician evaluation
  - Consider chest x-ray
  - Possible sputum culture
- [ ] **Reference to**: Pneumonia acute pathway, alert thresholds, complications section

---

## Scenario 4: HTN - Medication Titration

### Patient Presentation
- **Patient**: 58-year-old female with hypertensive urgency
- **Current**: Day 2 on oral antihypertensive (IV stopped yesterday)
- **BP readings today**: 142/88, 138/84, 145/90

### Question
"Patient's BP is controlled now (140s/80s). When can she transition to post-acute care?"

### Expected Response Elements
- [ ] **Current status**: BP approaching goal but not optimal (<130/80 target)
- [ ] **Transition criteria** (HTN acute → post-acute):
  - BP controlled <160/100 (met ✅)
  - No IV medications needed (met ✅)
  - Oral regimen stable (need 24-48 hrs confirmation)
  - Patient able to self-monitor BP at home (verify)
- [ ] **Recommendation**: Continue acute care 1-2 more days to confirm stability
- [ ] **Post-acute plan**:
  - 30-day BP monitoring
  - Twice daily BP measurements
  - HTN symptom questionnaire
  - Medication adherence tracking
- [ ] **Reference to**: HTN acute pathway, transition-to-postacute protocol

---

## Scenario 5: Diabetes - Hyperglycemia Alert

### Patient Presentation
- **Patient**: 45-year-old male, day 3 post-DKA resolution (now on subcutaneous insulin)
- **Glucose readings**: 18.5 mmol/L (333 mg/dL) fasting this morning
- **Symptoms**: Reports increased thirst, urination

### Question
"Glucose is 18.5 mmol/L. Is this a critical alert? What should I do?"

### Expected Response Elements
- [ ] **Alert level**: ≥16.7 mmol/L (300 mg/dL) = **critical alert**
- [ ] **Immediate actions**:
  - Check ketones (DKA relapse concern)
  - Review insulin adherence (did patient take doses?)
  - Assess for illness, infection (triggers hyperglycemia)
  - Check diabetes questionnaire for hyper symptoms
- [ ] **Escalation**:
  - If ketones ≥1.5 mmol/L → urgent physician evaluation (DKA risk)
  - If no ketones but persistent hyperglycemia → insulin dose adjustment
- [ ] **Monitoring**:
  - Recheck glucose in 2-4 hours after intervention
  - Increase monitoring frequency temporarily
- [ ] **Reference to**: Diabetes acute pathway, alert thresholds, diabetes questionnaire

---

## Scenario 6: DVT - Anticoagulation Concern

### Patient Presentation
- **Patient**: 62-year-old female, day 5 on IV heparin for DVT (right leg)
- **Report**: Patient notices increased bruising on arms, small amount of blood when brushing teeth

### Question
"DVT patient on heparin reports bruising and gum bleeding. Is this expected or concerning?"

### Expected Response Elements
- [ ] **Assessment needed**:
  - Severity of bleeding (minor vs major)
  - Gum bleeding: small amount with brushing = minor, acceptable
  - Bruising: location, size, pain, expanding?
  - Check for other bleeding signs (hematuria, melena, epistaxis)
  - Review DVT daily questionnaire responses
- [ ] **Minor bleeding** (expected):
  - Small bruises, minor gum bleeding with trauma
  - Continue anticoagulation with monitoring
- [ ] **Major bleeding** (critical):
  - Large expanding bruises, spontaneous bleeding, hematemesis, melena
  - Hold anticoagulation, urgent evaluation
- [ ] **Monitoring**:
  - Daily bleeding surveillance via questionnaire
  - Check aPTT (if on heparin) or anti-Xa level
- [ ] **Reference to**: DVT acute pathway, DVT questionnaire, anticoagulation monitoring

---

## Scenario 7: COVID-19 - Deterioration Warning

### Patient Presentation
- **Patient**: 59-year-old male, day 7 of COVID pneumonia (on 2L NC oxygen)
- **Alert**: SpO2 dropped to 91%, respiratory rate increased to 26/min
- **Symptoms**: Reports increased dyspnea with minimal activity

### Question
"COVID patient on day 7 with dropping SpO2 (91%) and increased RR (26). What does this mean?"

### Expected Response Elements
- [ ] **Clinical significance**: Day 5-10 = **high-risk window for deterioration**
  - "Silent hypoxemia" common in COVID
  - SpO2 <92% on oxygen = critical alert
  - RR >25/min = critical alert (both thresholds met)
- [ ] **Immediate actions**:
  - Increase oxygen to maintain SpO2 ≥92%
  - Assess for respiratory distress (work of breathing, use of accessory muscles)
  - Check COVID questionnaire for emergency symptoms
  - Review activity level (at rest vs with activity)
- [ ] **Escalation criteria**:
  - If increasing O2 requirement >4L NC → consider hospitalization
  - If respiratory distress, confusion, chest pain → **911/ED transfer**
- [ ] **Monitoring**:
  - Continuous SpO2 monitoring (Everion armband)
  - Increase virtual check-in frequency
- [ ] **Reference to**: COVID acute pathway, alert thresholds, COVID questionnaire (911 triggers)

---

## Edge Case Scenario 8: Comorbidities (CHF + COPD)

### Patient Presentation
- **Patient**: 75-year-old male with CHF + COPD
- **Admission**: CHF exacerbation (primary)
- **Symptoms**: Dyspnea, weight gain, but also has chronic cough and wheezing from COPD

### Question
"Patient has both CHF and COPD. How do I differentiate if dyspnea is from CHF fluid overload or COPD exacerbation?"

### Expected Response Elements
- [ ] **Use comorbidity matrix** for CHF + COPD overlap
- [ ] **CHF indicators**:
  - Weight gain (specific to CHF)
  - Orthopnea, PND
  - Response to diuretics (improves with diuresis)
  - Rales on exam
- [ ] **COPD indicators**:
  - Sputum production, color change
  - Wheezing
  - CAT score increase
  - No weight change
- [ ] **Monitoring both**:
  - Daily weights (CHF)
  - CAT score (COPD)
  - Both questionnaires
  - SpO2 target 88-92% (COPD baseline, not 95%+)
- [ ] **Treatment overlap**:
  - Be cautious with beta-blockers (good for CHF, may worsen COPD)
  - Use cardioselective beta-blockers only
- [ ] **Reference to**: CHF acute pathway (primary), COPD comorbidity notes, comorbidity matrix

---

## Edge Case Scenario 9: Borderline Values

### Patient Presentation
- **Patient**: 66-year-old female with CHF
- **BP reading**: 91/58 mmHg (threshold for hypotension is SBP <90)
- **Symptoms**: No dizziness, no orthostatic symptoms, tolerating well

### Question
"BP is 91/58. This is barely above the alert threshold of <90. Should I be concerned?"

### Expected Response Elements
- [ ] **Clinical context matters**:
  - Threshold is a guide, not absolute
  - Patient symptomatic? (no dizziness = reassuring)
  - Trending? (one reading vs consistent)
  - On diuretics? (expected mild drop)
- [ ] **Actions**:
  - Recheck BP (verify accuracy)
  - Ask about symptoms (dizziness, weakness)
  - Review recent diuretic doses
  - Check orthostatic BP if concerned
- [ ] **When to escalate**:
  - If symptomatic (dizzy, weak, confused) → urgent
  - If SBP drops below 90 → hold diuretics, clinical evaluation
  - If trending down over multiple readings → alert physician
- [ ] **Monitoring**:
  - Increase BP check frequency temporarily
  - Watch for symptoms
- [ ] **Reference to**: Alert thresholds (context section), CHF acute pathway

---

## Scenario 10: Transition Readiness

### Patient Presentation
- **Patient**: 70-year-old male with CHF exacerbation
- **Progress**: Day 8, euvolemic (back to baseline weight), off IV diuretics for 48 hours
- **Current**: On oral diuretics, stable vitals, no dyspnea at rest

### Question
"CHF patient is euvolemic and stable. Ready for post-acute transition?"

### Expected Response Elements
- [ ] **Transition criteria checklist** (CHF acute → post-acute):
  - ✅ Euvolemic (baseline weight achieved)
  - ✅ Off IV diuretics >24-48 hrs
  - ✅ On stable oral diuretic regimen
  - ✅ No dyspnea at rest
  - ✅ SpO2 >90% on room air
  - ? Patient able to perform daily weights at home
  - ? Understands medication regimen
- [ ] **Handoff process**:
  - Complete transition-to-postacute checklist
  - Provide post-acute care team with:
    - Baseline weight
    - Current medication list
    - KCCQ-12 baseline score
    - Comorbidities
  - Schedule day-1 post-discharge check-in
- [ ] **Post-acute plan**:
  - 30-day monitoring
  - Daily weights (most critical)
  - KCCQ-12 monthly
  - Medication adherence tracking
- [ ] **Reference to**: Transition-to-postacute protocol, CHF post-acute pathway

---

## Verification Checklist

For each scenario, the skill response should:

- [ ] **Identify correct disease pathway** (acute vs post-acute)
- [ ] **Reference appropriate threshold values** from alert-thresholds.md
- [ ] **Link to relevant questionnaire** when applicable
- [ ] **Provide clinical context** (not just numbers)
- [ ] **Include escalation criteria** (when to alert physician, when 911)
- [ ] **Cross-reference comorbidities** when relevant
- [ ] **Use evidence-based guidance** (guidelines cited)
- [ ] **Avoid medication dosing** (thresholds only, no prescriptive advice)
- [ ] **Maintain patient safety focus** (err on side of caution)

---

## Notes

- All patient data is **synthetic** - no real PHI
- Scenarios cover typical presentations, alerts, and edge cases
- Expected responses are guidelines - actual skill output may vary in wording but should cover key elements
- Use these scenarios for manual verification before each release
