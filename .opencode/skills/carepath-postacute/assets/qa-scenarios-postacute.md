# QA Scenarios - Carepath Post-Acute Care Skill

**Purpose**: Manual verification scenarios for the `carepath-postacute` skill covering all 7 disease pathways.

**Usage**: These scenarios test skill responses for post-discharge readmission prevention. Use synthetic data only - no real PHI.

---

## Scenario 1: CHF - KCCQ-12 Score Drop

### Patient Presentation
- **Patient**: 71-year-old female, day 12 post-discharge after CHF exacerbation
- **Baseline KCCQ-12**: 65/100 at discharge
- **Current KCCQ-12**: 52/100 (dropped 13 points)
- **Symptoms**: Reports increased fatigue, mild dyspnea with activities she could do last week

### Question
"CHF patient's KCCQ-12 score dropped from 65 to 52 in 2 weeks. What does this mean?"

### Expected Response Elements
- [ ] **Significance**: ≥10-point drop = clinically significant deterioration
  - 13-point drop = **meaningful QoL decline**
  - Strong predictor of readmission risk
- [ ] **Assessment needed**:
  - Check daily weights (any gain?)
  - Review CHF symptom questionnaire responses
  - Medication adherence (especially diuretics)
  - New symptoms? (orthopnea, PND, edema)
- [ ] **Actions**:
  - Urgent virtual visit with clinician
  - Review medication regimen for GDMT optimization
  - Possible diuretic adjustment
  - Increase monitoring frequency
- [ ] **Escalation criteria**:
  - If weight gain ≥3 lbs in 3 days → consider acute care transition
  - If worsening dyspnea at rest → urgent evaluation
- [ ] **Reference to**: CHF post-acute pathway, KCCQ-12 scoring interpretation, CHF questionnaire

---

## Scenario 2: COPD - CAT Score Trending

### Patient Presentation
- **Patient**: 68-year-old male, 45 days post-COPD exacerbation
- **CAT scores**: Day 1: 18, Day 14: 15, Day 30: 14, Day 45: 22
- **Current symptoms**: Increased cough, yellow sputum (was clear), more dyspnea

### Question
"COPD patient's CAT score went from 14 to 22 over 2 weeks. Is this a new exacerbation?"

### Expected Response Elements
- [ ] **CAT score interpretation**:
  - 0-10 = low impact, 11-20 = medium, 21-30 = high, 31-40 = very high
  - Jumped from "medium" (14) to "high" (22) = **significant worsening**
  - 8-point increase = clinically meaningful change
- [ ] **Exacerbation warning signs** (present):
  - ✅ Increased cough
  - ✅ Sputum color change (clear → yellow = purulent)
  - ✅ Increased dyspnea
  - ✅ CAT score increase
- [ ] **Assessment**:
  - Review COPD daily questionnaire
  - Check if patient used rescue inhaler more frequently
  - Any fever? (sign of infection)
  - SpO2 trend dropping?
- [ ] **Actions**:
  - Likely early COPD exacerbation → urgent physician evaluation
  - May need antibiotics (purulent sputum), increased steroids
  - Ensure patient has action plan (when to escalate)
- [ ] **Escalation**: If worsening → may need acute care transition
- [ ] **Reference to**: COPD post-acute pathway, CAT scoring, COPD questionnaire

---

## Scenario 3: Pneumonia - Relapse Surveillance

### Patient Presentation
- **Patient**: 52-year-old male, day 18 post-discharge for pneumonia
- **Course**: Improved well initially, back to normal activities
- **New symptoms**: Temp 38.2°C today, some cough returning, fatigue

### Question
"Pneumonia patient was doing well for 2 weeks, now has fever again. Relapse or new infection?"

### Expected Response Elements
- [ ] **Clinical context**:
  - Day 18 post-discharge = late for pneumonia relapse (usually days 3-7)
  - But post-pneumonia complications can occur
- [ ] **Differential**:
  - **Pneumonia relapse** (same organism)
  - **New pneumonia** (different organism)
  - **Other infection** (URI, UTI, etc.)
  - **Non-infectious fever** (less likely given cough)
- [ ] **Assessment**:
  - Review pneumonia questionnaire
  - Respiratory symptoms? (dyspnea, chest pain, sputum)
  - Check if patient completed full antibiotic course
  - SpO2 measurement
- [ ] **Red flags** requiring urgent evaluation:
  - High fever (>39°C)
  - Dyspnea, chest pain
  - SpO2 <92%
  - Confusion
- [ ] **Actions**:
  - Urgent virtual visit
  - Likely needs clinical evaluation ± chest x-ray
  - If stable, may manage outpatient; if unstable → ED/acute care
- [ ] **Reference to**: Pneumonia post-acute pathway, complications section

---

## Scenario 4: HTN - Blood Pressure Control

### Patient Presentation
- **Patient**: 60-year-old female, day 20 post-hypertensive urgency
- **BP readings** (twice daily): Morning 148/86, Evening 152/90 (average this week)
- **Medication**: Taking all meds as prescribed (reports 100% adherence)

### Question
"Patient is adherent to HTN meds but BP still averaging 150/88. What adjustments are needed?"

### Expected Response Elements
- [ ] **BP goal**: <130/80 for most patients (ACC/AHA 2017)
  - Current average ~150/88 = **above goal**
  - Not hypertensive urgency (that's ≥180/110), but suboptimal control
- [ ] **Assessment**:
  - Confirm adherence (pill counts, pharmacy refills)
  - Review HTN symptom questionnaire
  - Any symptoms? (headache, dizziness)
  - Lifestyle factors (salt intake, weight, activity)
  - Medication timing (taking at right times?)
- [ ] **GDMT optimization**:
  - 30-day post-acute period = time to titrate meds to goal
  - May need dose increase or add second agent
  - Physician evaluation for medication adjustment
- [ ] **Non-pharmacologic**:
  - Dietary sodium reduction
  - Weight loss if overweight
  - Exercise recommendations
- [ ] **Monitoring**:
  - Continue twice daily BP measurements
  - Reassess in 1-2 weeks after medication change
- [ ] **Reference to**: HTN post-acute pathway, GDMT adherence targets

---

## Scenario 5: Diabetes - Recurrent Hyperglycemia

### Patient Presentation
- **Patient**: 42-year-old male, day 25 post-DKA discharge
- **Glucose pattern**: Fasting 8-10 mmol/L, post-meal spikes to 14-16 mmol/L
- **Symptoms**: Occasional thirst, increased urination
- **Adherence**: Taking insulin ~80% of the time (admits missing doses)

### Question
"Diabetes patient has persistent hyperglycemia. Glucose control not achieved. What's the issue?"

### Expected Response Elements
- [ ] **Glucose targets**:
  - Fasting: 4-7 mmol/L (72-126 mg/dL)
  - Post-meal: <10 mmol/L (<180 mg/dL)
  - Current: fasting borderline, post-meal high
- [ ] **Root cause analysis**:
  - **Adherence issue**: 80% adherence = missing ~6 doses/month
  - Missing doses → inadequate coverage → hyperglycemia
- [ ] **Assessment**:
  - Review diabetes daily questionnaire
  - Why missing doses? (forgetfulness, side effects, cost, fear?)
  - Dietary intake (carb counting, portion sizes)
  - Activity level
- [ ] **Interventions**:
  - **Priority**: Address adherence barriers
  - Diabetes educator consultation
  - Simplify regimen if possible
  - Reminder systems, family support
  - Review injection technique
- [ ] **Monitoring**:
  - Continue QID glucose monitoring
  - Track adherence patterns
  - Reassess HbA1c at 90 days (outcome measure)
- [ ] **Escalation**: If persistent hyperglycemia despite adherence → medication adjustment
- [ ] **Reference to**: Diabetes post-acute pathway, medication adherence tracking

---

## Scenario 6: DVT - Anticoagulation Monitoring (Warfarin)

### Patient Presentation
- **Patient**: 55-year-old female, day 40 post-DVT on warfarin
- **INR history**: Week 1: 1.8, Week 2: 2.3, Week 3: 2.1, Week 4: 3.5, Week 6: 4.2
- **Symptoms**: No bleeding, no new swelling

### Question
"DVT patient on warfarin with INR 4.2 (therapeutic range 2-3). What should I do?"

### Expected Response Elements
- [ ] **INR interpretation**:
  - Target: 2-3 for DVT
  - Current: 4.2 = **supratherapeutic** (increased bleeding risk)
  - Not critically high (>5 = hold warfarin), but needs adjustment
- [ ] **Bleeding assessment**:
  - Review DVT questionnaire for bleeding signs
  - Any bruising, gum bleeding, hematuria, melena?
  - Currently asymptomatic = reassuring
- [ ] **Actions**:
  - Contact physician for warfarin dose adjustment (likely decrease)
  - Hold 1-2 doses or reduce weekly dose
  - Recheck INR in 3-5 days
  - Increase bleeding surveillance
- [ ] **Monitoring**:
  - Daily DVT questionnaire (bleeding questions)
  - Patient education: avoid NSAIDs, report any bleeding immediately
  - INR checks per physician protocol (weekly until stable)
- [ ] **Why INR fluctuates**:
  - Dietary vitamin K intake changes
  - Drug interactions
  - Illness
  - Medication adherence variability
- [ ] **Reference to**: DVT post-acute pathway, anticoagulation monitoring, DVT questionnaire

---

## Scenario 7: COVID-19 - Long COVID Screening

### Patient Presentation
- **Patient**: 47-year-old male, day 28 post-COVID diagnosis
- **Acute illness**: Resolved, no longer infectious
- **Lingering symptoms**: Severe fatigue, "brain fog," shortness of breath with exertion (wasn't there before COVID)

### Question
"COVID patient recovered from acute illness but has persistent fatigue and dyspnea 4 weeks later. Is this normal?"

### Expected Response Elements
- [ ] **Post-COVID timeline**:
  - Acute illness: Days 0-14
  - Recovery: Days 14-28
  - Persistent symptoms >4 weeks = **possible long COVID**
- [ ] **Long COVID symptoms** (common):
  - ✅ Fatigue (most common)
  - ✅ Cognitive dysfunction ("brain fog")
  - ✅ Dyspnea/exercise intolerance
  - Others: palpitations, headaches, joint pain
- [ ] **Assessment**:
  - Review COVID questionnaire responses
  - Functional impact (able to work, ADLs?)
  - SpO2 at rest and with exertion
  - Exclude other causes (anemia, deconditioning, pulmonary embolism)
- [ ] **Management**:
  - Document symptoms (long COVID screening)
  - Refer to long COVID clinic if available
  - Symptomatic management (graded exercise, pacing)
  - Possible additional workup (PFTs, echo, labs)
- [ ] **Monitoring duration**:
  - Original plan: 14 days
  - May extend monitoring if long COVID suspected
- [ ] **Reference to**: COVID post-acute pathway, long COVID surveillance section

---

## Scenario 8: Transition from Post-Acute to Acute Care

### Patient Presentation
- **Patient**: 73-year-old male with CHF, day 18 post-discharge
- **Symptoms**: 5-lb weight gain over 3 days, worsening dyspnea, orthopnea returned
- **Current**: On oral diuretics, not improving

### Question
"Post-acute CHF patient with 5-lb weight gain and worsening dyspnea. Does he need acute care again?"

### Expected Response Elements
- [ ] **Decompensation signs**:
  - ✅ Weight gain ≥3 lbs in 3 days (critical threshold)
  - ✅ Worsening dyspnea
  - ✅ Orthopnea returning
  - Not responding to oral diuretics
- [ ] **Escalation criteria** (post-acute → acute):
  - Requires IV diuresis (oral not sufficient)
  - Evidence of fluid overload despite outpatient management
  - Meets acute care eligibility criteria again
- [ ] **Assessment**:
  - Virtual visit or urgent in-person evaluation
  - Clinical exam (edema, rales, JVP)
  - Consider BNP if available
  - Review medication adherence (was he taking diuretics?)
- [ ] **Transition process**:
  - Urgent physician evaluation
  - Likely admit to acute care pathway (hospital-at-home or hospital)
  - Use transition-from-postacute protocol
  - Handoff: baseline weight, current meds, recent events
- [ ] **Root cause**:
  - Non-adherence? Dietary indiscretion? Infection trigger?
  - Medication optimization needed?
- [ ] **Reference to**: Transition-from-acute protocol (reverse direction), CHF acute pathway

---

## Scenario 9: Medication Adherence Coaching

### Patient Presentation
- **Patient**: 64-year-old female with HTN, day 10 post-discharge
- **Adherence data**: Taking BP meds 60% of days (missing 4-5 doses/week)
- **Reason**: "I forget," "Too many pills," "Feel fine without them"

### Question
"HTN patient only taking meds 60% of the time. How do I improve adherence?"

### Expected Response Elements
- [ ] **Adherence target**: >80% (current 60% = subtherapeutic)
  - Missing 40% of doses → BP unlikely to be controlled
  - Major risk factor for readmission
- [ ] **Barrier identification**:
  - **Forgetfulness**: Need reminder system
  - **Pill burden**: Simplify regimen if possible
  - **Feeling fine**: Education (HTN is "silent killer")
- [ ] **Interventions** (tiered approach):
  - **Reminders**: Phone alarms, pill organizer, family member reminders
  - **Simplification**: Once-daily dosing, combination pills if possible
  - **Education**: Explain consequences, long-term benefits
  - **Behavioral**: Link to daily habit (morning coffee, brushing teeth)
  - **Support**: Pharmacy sync, auto-refills
- [ ] **Monitoring**:
  - Daily adherence tracking via app/questionnaire
  - Follow-up at 1 week to assess improvement
  - Celebrate successes (positive reinforcement)
- [ ] **Post-acute role**:
  - Medication adherence = core post-acute outcome measure
  - Track as % adherence per week
  - Escalate to clinician if persistent non-adherence
- [ ] **Reference to**: HTN post-acute pathway, medication adherence section

---

## Scenario 10: Program Completion Criteria

### Patient Presentation
- **Patient**: 58-year-old male, day 28 post-COPD exacerbation
- **Status**:
  - CAT score stable at 12 (was 28 at admission, 18 at discharge)
  - No exacerbations since discharge
  - Using inhalers correctly and consistently
  - Follow-up appointment scheduled with pulmonologist

### Question
"COPD patient at day 28, doing well. Can he complete post-acute monitoring now or continue to 90 days?"

### Expected Response Elements
- [ ] **COPD post-acute duration**: Typically **90 days** (not 30)
  - Highest re-exacerbation risk in first 90 days post-discharge
  - National: 50% re-exacerbate within 90 days
- [ ] **Current status**:
  - Day 28 = less than halfway through monitoring
  - Doing well, but still high-risk period
- [ ] **Completion criteria** (COPD):
  - Completed full 90-day monitoring period
  - No exacerbations for sustained period
  - CAT score stable or improving
  - Established with pulmonologist for ongoing care
  - Medication adherence >80%
- [ ] **Recommendation**: **Continue to 90 days**
  - Patient is doing well (excellent progress)
  - But evidence supports 90-day monitoring for COPD
  - Can reduce monitoring intensity if stable (e.g., weekly check-ins instead of daily)
- [ ] **Transition to primary care**:
  - After 90 days, transition to routine pulmonology follow-up
  - Provide summary: exacerbation history, CAT trends, medication regimen
- [ ] **Reference to**: COPD post-acute pathway (duration section), transition criteria

---

## Verification Checklist

For each scenario, the skill response should:

- [ ] **Identify correct post-acute pathway** (30 vs 90 vs 14 days)
- [ ] **Interpret questionnaire scores** correctly (KCCQ-12, CAT, etc.)
- [ ] **Assess readmission risk factors** (weight gain, score drops, non-adherence)
- [ ] **Provide escalation guidance** (when to transition back to acute care)
- [ ] **Address medication adherence** (barriers and interventions)
- [ ] **Reference outcome measures** (30-day readmission, HbA1c, etc.)
- [ ] **Link to relevant resources** (questionnaires, transition protocols)
- [ ] **Focus on prevention** (readmission prevention is primary goal)
- [ ] **Maintain safety focus** (patient safety over convenience)

---

## Notes

- All patient data is **synthetic** - no real PHI
- Scenarios emphasize readmission prevention and patient self-management
- Post-acute care focuses on medication adherence, symptom surveillance, and timely escalation
- Expected responses are guidelines - actual skill output may vary in wording but should cover key elements
- Use these scenarios for manual verification before each release
