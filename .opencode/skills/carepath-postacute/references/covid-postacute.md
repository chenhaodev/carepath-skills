# COVID-19 Post-Acute Care Pathway

## Objective

Reduce risk of hospital admission, emergency department visits, and premature mortality in COVID-19 patients while optimizing patient comfort. This program targets patients diagnosed with COVID-19 who require additional support and are transitioning to or eligible for home-based treatment.

**Key Focus Areas**:
- Critical monitoring during days 5-10 (peak deterioration window)
- Early detection of respiratory decompensation and silent hypoxemia
- Identification of complications (bacterial superinfection, VTE, myocarditis)
- Long COVID symptom surveillance (symptoms persisting >4 weeks)

---

## Duration

**14 days** from confirmed diagnosis

**Rationale for shorter duration**:
- Peak severity occurs days 8-12; most complications manifest within first 14 days
- Lower readmission risk compared to CHF/COPD (acute viral illness vs chronic disease)
- Long COVID surveillance transitions to outpatient follow-up after 14 days

---

## Eligibility

### Inclusion Criteria

- **Age**: 18-75 years
- **Confirmed COVID-19 diagnosis** (PCR or rapid antigen test)
- **Eligible for outpatient monitoring**: Stable or improving symptoms
- **Oxygen status**: 
  - SpO2 ≥92% on ≤4L nasal cannula (NC), OR
  - Requires <6 hours/day of supplemental oxygen
- **Functional capacity**: Ability to complete in-app tasks and questionnaires (in offered languages) and use required devices

### Exclusion Criteria

- **Severe hypoxemia**: SpO2 <92% despite 4L NC oxygen
- **Respiratory failure**: Requiring high-flow nasal cannula, BiPAP, or mechanical ventilation
- **Hemodynamic instability**: Hypotension requiring IV fluids or vasopressors
- **Altered mental status**: Confusion, disorientation suggesting hypoxic encephalopathy
- **Critical comorbidities**: Decompensated heart failure, severe COPD exacerbation, dialysis-dependent renal failure
- **Social factors**: No reliable internet/smartphone access, unsafe home environment, inability to perform self-care

---

## Primary Outcome Measures

| Outcome Measure | Timeframe | Target |
|-----------------|-----------|--------|
| **Hospital Admission Rate** | 30 days | <5% of enrolled patients |
| **Emergency Department Visits** | 30 days | <10% of enrolled patients |
| **Mortality** | 30 days | <1% of enrolled patients |
| **Mortality** | 90 days | <2% of enrolled patients |
| **Patient Satisfaction Score** | End of 14-day program | ≥4.5/5.0 |

---

## Care Protocol Details

### Devices

#### Required Monitoring Devices

| Device | Purpose | Data Captured | Monitoring Frequency |
|--------|---------|---------------|---------------------|
| **Everion Armband** | Continuous physiologic monitoring | HR, RR, SpO2, skin temperature, activity levels | Continuous (24/7) |
| **Thermometer** | Temperature measurement | Core body temperature | Twice daily (morning, evening) |

**Reference**: See [`shared/devices.md`](../../shared/devices.md) for detailed device specifications and setup instructions.

**Device Distribution**:
- Mailed to patient within 24 hours of enrollment (or provided at discharge)
- Setup support via telehealth or video call
- Backup devices available if malfunction occurs

---

### Physiologic Monitoring

#### Continuous Monitoring (Everion Armband)

**Parameters tracked 24/7**:

| Parameter | Normal Range | Alert Threshold | Critical Threshold |
|-----------|--------------|-----------------|-------------------|
| **SpO2** | ≥95% | <94% | <92% |
| **Heart Rate** | 60-100 bpm | <50 or >110 bpm | <45 or >130 bpm |
| **Respiratory Rate** | 12-20/min | >22/min | >25/min or <10/min |
| **Skin Temperature** | 36.1-37.2°C | >37.5°C | >38.5°C |

**Activity Level**:
- Track daily activity (steps, exertion)
- Sudden decrease in activity may indicate decompensation

**Reference**: See [`shared/alert-thresholds.md`](../../shared/alert-thresholds.md) for complete threshold table.

#### Intermittent Monitoring

**Temperature checks**:
- **Twice daily** (morning upon waking, evening before bed)
- Document in patient app diary
- Persistent fever >7 days → triggers clinical review

---

### Daily Tasks & Symptom Triaging

#### Daily Patient Tasks

**Morning (upon waking)**:
1. Measure temperature with thermometer → log in app
2. Complete COVID-19 Daily Symptom Checker (questionnaire)
3. Check Everion armband is properly positioned and charged

**Evening (before bed)**:
1. Measure temperature → log in app
2. Review daily activity summary from armband
3. Charge Everion armband overnight

**Reference**: Full questionnaire available at [`shared/questionnaires/covid-questionnaire.md`](../../shared/questionnaires/covid-questionnaire.md)

#### Symptom Questionnaire Components

**Section A: Emergency Symptoms (911 Criteria)**
- Blue lips/skin/nails (cyanosis)
- Severe chest pain or pressure
- Difficulty breathing (gasping, unable to speak)
- New confusion or disorientation
- Unconsciousness or difficulty waking
- Signs of shock (low blood pressure, dizziness, cold/clammy skin)

**IF ANY EMERGENCY SYMPTOM → IMMEDIATE 911 CALL, STOP QUESTIONNAIRE**

**Section B: Respiratory Symptoms**
- Dyspnea severity (at rest, with activity, worsening)
- Cough (new onset, increasing frequency, productive vs dry)
- Wheezing
- Chest tightness

**Section C: Systemic Symptoms**
- Fever (subjective, measured temperature)
- Muscle aches, fatigue, headache
- Loss of taste/smell (anosmia/ageusia)
- GI symptoms (nausea, vomiting, diarrhea)
- Sore throat, congestion

---

### Patient Education

**COVID-19 Education Modules** (delivered via patient app):

#### Module 1: Disease Timeline & Progression (Day 1)
- Expected symptom progression (days 1-5 upper respiratory, days 5-10 potential worsening)
- Critical window (days 5-10): When to watch most closely
- Recovery timeline (14+ days)

#### Module 2: When to Contact Provider (Day 2)
- Worsening dyspnea (SpO2 <94%)
- Persistent high fever >40°C or fever lasting >7 days
- Chest pain, severe headache, confusion
- Symptom improvement followed by sudden worsening (days 7-10)

#### Module 3: When to Call 911 (Day 3)
- Emergency warning signs (blue lips, severe difficulty breathing, chest pain)
- Do NOT drive yourself to hospital if emergency symptoms present
- Prone positioning while waiting for EMS (if tolerated)

#### Module 4: Isolation & Transmission Prevention (Day 4)
- Current CDC isolation recommendations
- Household transmission prevention
- When isolation can end (criteria-based, not just time-based)

#### Module 5: Long COVID Awareness (Day 10)
- Symptoms of long COVID (fatigue, brain fog, POTS, dyspnea)
- When to report persistent symptoms (>4 weeks)
- Multidisciplinary long COVID clinic referral process

---

### Alerts, Escalations, & Care Coordination

#### Daily Care Team Monitoring

**Clinical team reviews daily**:
- Patient questionnaire responses (emergency symptoms flagged in real-time)
- Physiologic alerts from Everion armband
- Temperature trends (fever curve)
- Patient task compliance (missed questionnaires or vital checks)
- Comorbidity monitoring (diabetes, HTN, COPD, CHF)

#### Alert Types & Escalation Protocol

**Reference**: See [`shared/alert-thresholds.md`](../../shared/alert-thresholds.md) for detailed escalation pathways.

| Alert Level | Criteria | Response Time | Intervention |
|-------------|----------|---------------|--------------|
| **CRITICAL (Red)** | • SpO2 <92%<br>• RR >25/min<br>• Emergency symptom (Section A)<br>• Skin temp >39°C sustained | **Immediate** (within 5 min) | • Call patient immediately<br>• Instruct to call 911 if emergency symptoms<br>• Urgent video visit<br>• Physician notification |
| **URGENT (Orange)** | • SpO2 92-93%<br>• RR 23-25/min<br>• HR >130 or <50 bpm<br>• Fever >38.5°C<br>• Worsening dyspnea (Section B) | **Within 1 hour** | • Video visit same day<br>• Assess need for oxygen therapy<br>• Consider antiviral therapy (if within 5 days)<br>• Possible ED referral |
| **ADVISORY (Yellow)** | • SpO2 94%<br>• RR 21-22/min<br>• Low-grade fever (37.5-38.5°C)<br>• Decreased activity | **Within 4 hours** | • Phone or chat outreach<br>• Increase monitoring frequency<br>• Patient education reinforcement |

**Additional Alert Triggers**:

**Trending Alerts** (pattern-based):
- **SpO2 decline**: Drop ≥3% over 24 hours (even if still >94%)
- **Fever pattern**: Biphasic fever (improves, then recurs days 7-10) → bacterial superinfection
- **Activity decline**: >50% decrease in daily steps for 2+ consecutive days → worsening disease

**Non-compliance Alert**:
- Missed questionnaire >24 hours → Outreach to assess patient status
- Everion armband not transmitting data >6 hours → Device troubleshooting or replacement

#### Support & Intervention Channels

**Synchronous**:
- **Video visits**: For urgent assessments, symptom triage, treatment decisions
- **Phone calls**: For critical alerts, emergency symptom escalation
- **Crisis hotline**: 24/7 nurse line for after-hours concerns

**Asynchronous**:
- **In-app chat**: For non-urgent questions, medication clarification, general support
- **Secure messaging**: Care team can send reminders, education materials, trend summaries

---

### Complications or Adverse Events

**Monitor for and manage**:

#### Respiratory Complications

**Progressive COVID Pneumonia**:
- **Presentation**: Worsening dyspnea, declining SpO2, increased RR
- **Peak risk**: Days 5-10 of illness
- **Action**: Urgent evaluation, chest imaging (CXR or CT), possible hospital admission
- **May require**: Oxygen therapy, remdesivir, dexamethasone

**Bacterial Superinfection**:
- **Presentation**: Biphasic fever (improves, then worsens), productive cough (new purulent sputum), leukocytosis
- **Timing**: Typically days 7-14
- **Common pathogens**: *Streptococcus pneumoniae*, *Staphylococcus aureus* (including MRSA), *Haemophilus influenzae*
- **Action**: Sputum culture, initiate empiric antibiotics (e.g., ceftriaxone + azithromycin)

#### Cardiovascular Complications

**Myocarditis/Pericarditis**:
- **Presentation**: Chest pain (pleuritic or pressure-like), troponin elevation, ECG changes
- **Screening**: Any chest pain → ECG, troponin, echocardiogram
- **Management**: NSAID avoidance, possible corticosteroids, cardiology referral

**Venous Thromboembolism (VTE)**:
- **Risk**: COVID-19 is a hypercoagulable state (risk 3-5x normal)
- **Presentation**:
  - **DVT**: Unilateral leg swelling, pain, warmth
  - **PE**: Sudden dyspnea, chest pain, hemoptysis, tachycardia
- **High-risk patients**: Immobilized, obese (BMI >30), prior VTE, active cancer
- **Prophylaxis**: Consider low-dose aspirin or prophylactic anticoagulation in high-risk patients (per physician)
- **Action if suspected**: Urgent D-dimer, Doppler ultrasound (DVT), CT pulmonary angiogram (PE)

#### Neurological Complications

**COVID-Associated Encephalopathy**:
- **Presentation**: Confusion, disorientation, memory deficits, "brain fog"
- **Mechanism**: Hypoxemia, systemic inflammation, direct CNS involvement
- **Screening**: Daily confusion assessment via questionnaire Section A

**Stroke**:
- **Risk**: COVID increases ischemic stroke risk (hypercoagulability, endothelial dysfunction)
- **Presentation**: Sudden weakness, facial droop, slurred speech, vision changes
- **Action**: Immediate 911 call, stroke protocol activation

#### Systemic Complications

**Dehydration & Acute Kidney Injury**:
- **Causes**: Fever, decreased oral intake, vomiting/diarrhea
- **Screening**: Urine output monitoring, signs of dehydration (dry mouth, dizziness, dark urine)
- **Management**: Encourage oral hydration, electrolyte monitoring, possible IV fluids

**Worsening Comorbidities**:
- **Diabetes**: Hyperglycemia exacerbation, DKA risk
- **Hypertension**: BP lability, medication adjustments needed
- **COPD/Asthma**: Exacerbation from viral infection
- **CHF**: Fluid overload from reduced activity, myocarditis

---

### Long COVID Surveillance

**Definition**: Symptoms persisting >4 weeks from initial infection (CDC definition)

**Common Long COVID Symptoms**:
- **Cardiopulmonary**: Persistent dyspnea, chest pain, palpitations, exercise intolerance
- **Neurological**: "Brain fog," memory/concentration issues, headaches, dysautonomia (POTS)
- **General**: Profound fatigue, post-exertional malaise
- **Sensory**: Persistent anosmia/ageusia

**Screening**:
- At **Day 14 final assessment**: Questionnaire to assess symptom resolution vs persistence
- If symptoms persist beyond 4 weeks → Referral to Long COVID clinic or multidisciplinary care

**Risk Factors for Long COVID**:
- Severe acute COVID (hospitalized, oxygen requirement)
- Female sex
- Pre-existing comorbidities (obesity, diabetes, autoimmune disease)
- Age >50

**Management**:
- Multidisciplinary approach (pulmonology, cardiology, neurology, rehab medicine)
- Graded exercise therapy (caution with post-exertional malaise)
- Symptom-based treatment (POTS → fludrocortisone, dyspnea → pulmonary rehab)

---

### Comorbidity-Specific Considerations

**Reference**: See [`shared/comorbidity-matrix.md`](../../shared/comorbidity-matrix.md) for detailed cross-disease interactions.

#### COVID-19 + Diabetes
- **Risk**: Hyperglycemia worsens COVID outcomes (impaired immune response, increased ACE2 expression)
- **Monitoring**: Daily glucose checks (fasting, bedtime), ketone monitoring if glucose >250 mg/dL
- **Complications**: Higher risk of DKA, severe COVID pneumonia
- **Management**: Tighter glucose control (target <180 mg/dL), insulin adjustment, avoid SGLT-2 inhibitors (DKA risk)

#### COVID-19 + Hypertension
- **Risk**: Poorly controlled HTN associated with worse COVID outcomes
- **Monitoring**: Daily BP checks (morning, evening)
- **Medication interactions**: ACE inhibitors/ARBs controversial (now recommended to continue)
- **Alert**: Hypotension may indicate shock → urgent evaluation

#### COVID-19 + COPD/Asthma
- **Risk**: Higher risk of severe respiratory complications, bacterial superinfection
- **Monitoring**: Baseline low SpO2 in COPD → adjust thresholds (e.g., alert if SpO2 <90% instead of <94%)
- **Management**: Continue baseline inhalers, add systemic corticosteroids early if exacerbation
- **Complication**: COVID + COPD exacerbation may mimic CHF (BNP testing helpful)

#### COVID-19 + CHF
- **Risk**: Myocardial stress from hypoxemia, myocarditis risk, fluid overload
- **Monitoring**: Daily weights, BNP trending, lower threshold for dyspnea escalation
- **Complications**: Acute decompensated heart failure (ADHF) vs COVID pneumonia (both cause dyspnea)
- **Management**: Diuretic adjustment, oxygen support, cardiology consultation

#### COVID-19 + DVT History
- **Risk**: COVID is hypercoagulable → reactivation or extension of prior DVT, new PE
- **Prophylaxis**: Consider therapeutic anticoagulation (vs prophylactic) if prior VTE
- **Monitoring**: Daily leg swelling checks, low threshold for Doppler ultrasound if symptoms
- **Duration**: Extended anticoagulation (3-6 months post-COVID in high-risk patients)

---

## Transition Criteria

### Transition to Acute Care (Escalation)

**Patient requires transfer to Acute Care Pathway if**:

1. **Respiratory failure**:
   - SpO2 <92% despite 4L NC oxygen
   - Respiratory rate >30/min sustained
   - Requiring >6L oxygen or high-flow nasal cannula

2. **Hemodynamic instability**:
   - Hypotension (SBP <90 mmHg) requiring IV fluids
   - Tachycardia >130 bpm sustained

3. **Severe complications**:
   - Suspected PE (sudden dyspnea, chest pain, tachycardia)
   - Myocarditis (chest pain + troponin elevation + ECG changes)
   - Bacterial superinfection requiring IV antibiotics
   - Acute decompensated heart failure

4. **Neurological deterioration**:
   - New confusion, disorientation, altered mental status
   - Suspected stroke (focal deficits, slurred speech)

5. **Social factors**:
   - Patient unable to manage home monitoring
   - Unsafe home environment
   - Non-compliance with daily tasks

**Transition Process**:
- Immediate physician notification
- Arrange urgent ED evaluation or direct hospital admission
- Transfer physiologic data and symptom trends to inpatient team
- Maintain remote monitoring until patient arrives at hospital

**Reference**: See [`transition-from-acute.md`](transition-from-acute.md) for detailed handoff protocol.

---

### Program Completion (Day 14)

**Patient successfully completes Post-Acute Care Pathway if**:

1. **Symptom improvement**:
   - No emergency symptoms (Section A) for ≥7 days
   - Dyspnea stable or improving
   - Fever resolved (afebrile >48 hours)

2. **Stable physiology**:
   - SpO2 >95% on room air
   - No critical alerts in past 3 days
   - Temperature <37.5°C for 48 hours

3. **Isolation criteria met**:
   - ≥5 days from symptom onset AND
   - Fever-free for 24 hours (without antipyretics) AND
   - Symptoms improving

**Final Assessment**:
- Video visit with care team
- Review symptom trajectory and complication screening
- **Long COVID screening**: Assess for persistent symptoms (>4 weeks)
- Transition back to primary care physician (PCP)
- Provide discharge summary with COVID course, complications, medications

**Follow-Up**:
- PCP appointment within 7-14 days post-completion
- Pulmonary function testing (if dyspnea persists) at 4-6 weeks
- Long COVID clinic referral if symptoms persist >4 weeks

---

### Transition Back from Acute Care (Step-Down)

**Patient may return to Post-Acute Care Pathway from Acute Care if**:

1. **Stabilized in acute setting**:
   - Oxygen requirement reduced to ≤4L NC (or weaned to room air)
   - Hemodynamically stable (SBP >100 mmHg, HR <110 bpm)
   - No active complications requiring IV therapy

2. **Remaining post-acute days**:
   - If acute care consumed <10 days, complete remaining days in post-acute pathway
   - If acute care ≥10 days, consider extending post-acute monitoring to 14 days from discharge

3. **Patient meets original eligibility criteria**:
   - Functional capacity restored
   - Safe home environment
   - Able to use devices and complete tasks

**Step-Down Process**:
- Confirm device functionality (Everion armband, thermometer)
- Review updated medication list (new anticoagulation, antibiotics, etc.)
- Adjust alert thresholds based on new baseline (e.g., home oxygen → SpO2 target 92%)
- Intensify monitoring first 48 hours post-discharge (twice daily check-ins)

---

## Other Recommended Care

**N/A** - All essential care components integrated into protocol above.

**Optional Adjuncts**:
- **Mental health support**: Telehealth counseling for anxiety, depression, PTSD related to COVID illness
- **Physical therapy**: Post-COVID reconditioning for patients with prolonged immobility or severe deconditioning
- **Nutritional support**: For patients with prolonged GI symptoms or significant weight loss

---

## Key Differences from Other Post-Acute Pathways

| Feature | COVID Post-Acute | CHF/COPD/DVT Post-Acute |
|---------|-----------------|------------------------|
| **Duration** | 14 days | 30-90 days |
| **Disease Course** | Acute viral illness (self-limited in most) | Chronic disease management |
| **Peak Risk Period** | Days 5-10 | Throughout monitoring period |
| **Readmission Risk** | Lower (5-10%) | Higher (20-30%) |
| **Primary Complication** | Respiratory decompensation, VTE | Disease-specific exacerbations |
| **Long-Term Sequelae** | Long COVID (20-30% of patients) | Chronic disease progression |
| **Monitoring Focus** | Silent hypoxemia, fever curve, symptom trajectory | Chronic vital signs, weight, adherence |

---

## Clinical Pearls

1. **Critical Window Days 5-10**: Patients often feel better days 1-5, then suddenly deteriorate days 5-10 → Do NOT reduce monitoring intensity during this window.

2. **Silent Hypoxemia**: COVID is unique in causing severe hypoxemia (SpO2 <92%) without dyspnea → ALWAYS check SpO2 even if patient denies shortness of breath.

3. **Prone Positioning**: Simple intervention that can improve SpO2 by 2-5% → Educate patients to lie on stomach if SpO2 drops.

4. **Antiviral Therapy Window**: Paxlovid effective ONLY if started within 5 days of symptom onset → Early identification and treatment critical.

5. **Biphasic Fever**: Fever improving then recurring days 7-10 is RED FLAG for bacterial superinfection → Urgent evaluation.

6. **VTE Risk**: COVID is hypercoagulable state → Low threshold for D-dimer, Doppler ultrasound if any leg swelling or sudden dyspnea.

7. **Long COVID**: ~20-30% develop persistent symptoms → Screen ALL patients at day 14, refer to multidisciplinary clinic if symptoms persist >4 weeks.

8. **Comorbidity Amplification**: COVID + Diabetes or COVID + HTN or COVID + COPD = significantly worse outcomes → Lower escalation threshold for these patients.

---

## References

- CDC COVID-19 Emergency Warning Signs
- NIH COVID-19 Treatment Guidelines (updated regularly)
- WHO Clinical Management of COVID-19: Living Guideline
- IDSA Guidelines on the Treatment and Management of Patients with COVID-19
- Carepath-Prod.pdf: COVID-19 Post-Acute Care Pathway (lines 1263-1360)

---

**Protocol Version**: 1.0  
**Last Updated**: 2026-02-01  
**Next Review**: Quarterly (or as new evidence emerges)
