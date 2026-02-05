# QA Scenarios: Oncology Care Pathways

**Version**: 1.0
**Purpose**: Validate `carepath-oncology` skill triggers, decision logic, and protocol adherence.
**Usage**: Use these scenarios to test the skill's response to various clinical presentations.

---

## Scenario 1: Febrile Neutropenia - Medical Emergency

**Clinical Presentation**:
- **Patient**: 58-year-old female with Stage III breast cancer
- **Treatment**: Received dose-dense AC chemotherapy (Adriamycin/Cyclophosphamide) 10 days ago
- **Call**: Patient phones at 9 PM reporting fever of 38.4°C (101.1°F), chills, and fatigue
- **History**: No cough, no dysuria, no diarrhea. Lives alone.

**Trigger Analysis**:
- Keywords: "chemotherapy", "fever", "neutropenia" → Auto-loads `carepath-oncology` skill
- Time-sensitive: 10 days post-chemo = nadir (expected neutropenia)
- Red flag: Fever ≥38°C in immunosuppressed patient

**Decision Tree**:
1. **Primary symptom**: Fever → Reference [`../references/symptom-febrile-neutropenia.md`](../references/symptom-febrile-neutropenia.md)
2. **Check eligibility**: Active chemo within 4 weeks? ✅ YES
3. **Red Flag Assessment**: Temp ≥38°C? ✅ YES → GRADE 4 EMERGENCY
4. **Check alert thresholds**: See [`../../shared/alert-thresholds.md`](../../shared/alert-thresholds.md)
   - Fever ≥38°C in neutropenic patient = IMMEDIATE ACTION
5. **Protocol**: See [`../../shared/nurse-response-protocols.md`](../../shared/nurse-response-protocols.md) - Febrile Neutropenia Protocol

**Action Plan** (Immediate - within 15 minutes):
1. ✅ **Do NOT wait** for ANC confirmation (assume neutropenic)
2. ✅ **Direct to Emergency Department NOW**
   - "Mrs. [Name], you need to go to the Emergency Department immediately. Do not drive yourself - call 911 or have someone take you."
3. ✅ **Notify oncologist on-call** immediately
4. ✅ **Call ahead to ED**: "Febrile neutropenia patient en route, recent AC chemo Day +10"
5. ✅ **Document**:
   - Time of call: 9:00 PM
   - Temperature: 38.4°C
   - Chemo: AC Day +10
   - Action: Directed to ED, oncologist notified

**Expected Outcome**:
- Door-to-antibiotic time: <60 minutes ("Golden Hour")
- Blood cultures obtained before antibiotics
- Empiric broad-spectrum antibiotics started (e.g., Cefepime or Pip-Tazo)
- Admission for monitoring until afebrile >24h and ANC recovering

**Key Learning Points**:
- ⚠️ NEVER delay febrile neutropenia patients for lab confirmation
- ⚠️ Day 7-14 post-chemo = highest neutropenia risk
- ⚠️ Every minute counts - antibiotics within 60 min = mortality reduction

---

## Scenario 2: Uncontrolled Nausea - Urgent Intervention

**Clinical Presentation**:
- **Patient**: 62-year-old male with colon cancer receiving FOLFOX (5-FU, Leucovorin, Oxaliplatin)
- **Day**: Day 3 post-infusion (still has 5-FU pump attached)
- **Complaint**: "I can't stop throwing up. I haven't eaten in 2 days. I'm so weak."
- **History**: Taking ondansetron 8mg Q8H, tried ginger tea, no relief

**Trigger Analysis**:
- Keywords: "chemotherapy", "nausea", "vomiting", "FOLFOX" → carepath-oncology skill
- Duration: 2 days of inadequate oral intake → dehydration risk
- Current management: Failing first-line antiemetic

**Decision Tree**:
1. **Primary symptom**: Nausea/Vomiting → Reference [`../references/symptom-nausea-vomiting.md`](../references/symptom-nausea-vomiting.md)
2. **CTCAE Grading**:
   - Unable to eat for 2 days = GRADE 3 (inadequate oral intake, IV fluids indicated)
3. **Red Flag Assessment**: 
   - Dehydration signs? → Ask about dizziness, dark urine, decreased urination
   - Weight loss >5%? → Check baseline weight
4. **Alert threshold**: Grade 3 = Hospitalization/IV intervention indicated
5. **Questionnaire**: See [`../../shared/questionnaires/oncology-questionnaire.md`](../../shared/questionnaires/oncology-questionnaire.md) - Section B

**Action Plan**:
1. ✅ **Escalate antiemetics**:
   - Add Metoclopramide 10mg PO/IV Q6H
   - Add Dexamethasone 8mg PO/IV daily
   - Consider Olanzapine 5mg PO daily (if refractory)
2. ✅ **Hydration assessment**:
   - If orthostatic or unable to tolerate PO → IV hydration needed
   - Chemo clinic same-day vs. ED (time-dependent)
3. ✅ **Electrolyte check**: Order BMP (hypokalemia common)
4. ✅ **Notify oncologist**: Dose reduction consideration for next cycle
5. ✅ **Patient education**:
   - Small, frequent meals when able
   - Avoid strong odors
   - Cool, bland foods (crackers, popsicles)

**Expected Outcome**:
- IV hydration + aggressive antiemetics (metoclopramide + dexamethasone)
- Symptom improvement within 24 hours
- BMP shows K+ 3.2 → Repleted
- Future cycles: Add olanzapine prophylaxis

**Key Learning Points**:
- ⚠️ Grade 3 nausea = NOT manageable at home
- ⚠️ FOLFOX = moderate-high emetogenic potential (delayed nausea Days 2-5)
- ⚠️ Olanzapine often more effective than ondansetron for breakthrough CINV

---

## Scenario 3: CIPN with Functional Impairment - Safety Focus

**Clinical Presentation**:
- **Patient**: 55-year-old female with ovarian cancer, completed 6 cycles of carboplatin/paclitaxel 2 months ago
- **Complaint**: "My feet are so numb I can't feel the floor. I almost fell twice this week."
- **Symptoms**: Bilateral glove-stocking numbness, difficulty with buttons, dropping objects
- **Current**: No pain medications, frustrated with persistent symptoms

**Trigger Analysis**:
- Keywords: "neuropathy", "numbness", "chemotherapy", "paclitaxel" → carepath-oncology skill
- Post-treatment: CIPN often worsens 1-3 months after last dose ("coasting phenomenon")
- Safety concern: Fall risk from sensory loss

**Decision Tree**:
1. **Primary symptom**: Peripheral Neuropathy → Reference [`../references/symptom-neuropathy.md`](../references/symptom-neuropathy.md)
2. **CTCAE Grading**:
   - Sensory loss + functional impairment (difficulty with fine motor) = GRADE 2
   - Near-falls = HIGH FALL RISK
3. **Assessment**:
   - Sensory: Glove-stocking distribution (classic CIPN)
   - Motor: Button difficulty, dropping objects (fine motor affected)
   - Autonomic: Check for constipation, orthostatic hypotension
4. **Comorbidity check**: See [`../../shared/comorbidity-matrix.md`](../../shared/comorbidity-matrix.md) - Cancer + Diabetes section
   - Does patient have diabetes? (Additive neuropathy risk)

**Action Plan**:
1. ✅ **Pharmacologic management**:
   - Start Duloxetine 30mg daily x 1 week, then 60mg daily (first-line for CIPN)
   - Alternative: Gabapentin 300mg TID if duloxetine contraindicated
2. ✅ **Safety interventions** (CRITICAL):
   - Home safety assessment: Remove throw rugs, improve lighting
   - Assistive devices: Consider cane for ambulation
   - Non-slip footwear, grab bars in bathroom
   - Fall risk education: "Use handrails, avoid uneven surfaces"
3. ✅ **Rehabilitation referral**:
   - Physical therapy: Gait training, balance exercises
   - Occupational therapy: Adaptive devices for fine motor tasks
4. ✅ **Monitoring**:
   - Neurologic exam monthly
   - Document progression vs. stability
   - Questionnaire: Daily symptom check for worsening

**Expected Outcome**:
- Duloxetine initiated, symptom improvement in 4-6 weeks (partial)
- Home safety modifications completed
- PT/OT improve functional status
- No falls over next 3 months
- CIPN Grade 2 → Stable (unlikely to fully resolve)

**Key Learning Points**:
- ⚠️ CIPN is often IRREVERSIBLE (manage symptoms + safety)
- ⚠️ "Coasting" = Worsening after chemo ends (lasts 3-6 months)
- ⚠️ Fall prevention > Pain control (sensory CIPN often painless but dangerous)
- ⚠️ Duloxetine = only FDA-approved med for CIPN

---

## Scenario 4: Cancer-Related Distress - Suicide Risk Assessment

**Clinical Presentation**:
- **Patient**: 48-year-old male with metastatic lung cancer, diagnosed 6 weeks ago
- **Questionnaire screening**: Distress Thermometer = 9/10, PHQ-2 positive for both questions
- **Follow-up call**: Patient tearful, states "I can't do this anymore. What's the point?"
- **C-SSRS screening**: Endorses suicidal ideation, has thought about pills, but "I wouldn't actually do it... I have kids."

**Trigger Analysis**:
- Keywords: "depression", "anxiety", "distress", "suicidal" → carepath-oncology skill
- Red flag: Suicidal ideation with method → URGENT
- Context: New diagnosis, likely anticipatory grief + existential distress

**Decision Tree**:
1. **Primary symptom**: Distress/Depression → Reference [`../references/symptom-distress.md`](../references/symptom-distress.md)
2. **Screening tools**:
   - Distress Thermometer: 9/10 (≥4 = clinically significant)
   - PHQ-2: 2/2 positive → Full PHQ-9 needed
   - C-SSRS: MODERATE RISK (ideation + method, no plan/intent, denies preparatory behavior)
3. **Risk stratification**: See [`../../shared/nurse-response-protocols.md`](../../shared/nurse-response-protocols.md) - Suicide Risk Protocol
   - 🟠 MODERATE RISK = Same-day psychiatry consult required

**Action Plan** (Immediate):
1. ✅ **DO NOT END CALL** until safety plan in place
2. ✅ **Same-day psychiatry consult**:
   - Call hospital psychiatry or crisis line for urgent appointment TODAY
   - If unavailable same-day → ED evaluation
3. ✅ **Safety assessment**:
   - "Do you have pills at home that you've thought about using?"
   - "Can we have someone remove those medications temporarily?"
   - "Is there someone who can stay with you today?"
4. ✅ **Create safety plan**:
   - Crisis hotline: 988 (Suicide & Crisis Lifeline)
   - Contact person: [Wife's name and phone]
   - Remove means: Family to secure medications
   - Commitment: "Will you promise to call 988 or go to ED if thoughts worsen?"
5. ✅ **Notify care team**:
   - Oncologist (aware of distress, may adjust treatment discussions)
   - Medical Social Worker (psychosocial support, resources)
   - Assign case manager: Daily check-in calls until psychiatry seen
6. ✅ **Document thoroughly**:
   - C-SSRS score and risk level
   - Safety plan elements
   - Who was notified and when
   - Next contact time

**Expected Outcome**:
- Psychiatry sees patient same day or next morning
- Starts SSRI (e.g., Escitalopram 10mg) + referral to cancer psychologist
- Weekly therapy sessions initiated
- MSW connects with palliative care for goals-of-care discussion
- Daily check-ins for 1 week, then taper based on stability

**Key Learning Points**:
- ⚠️ 40% of cancer patients have significant distress (UNDER-recognized)
- ⚠️ Suicide risk 2x higher in cancer patients vs. general population
- ⚠️ C-SSRS MODERATE RISK = Same day intervention (NOT "schedule appointment")
- ⚠️ Method + ideation (even without plan) = URGENT, not routine referral
- ⚠️ Never leave patient alone if HIGH risk; MODERATE risk needs family notification
