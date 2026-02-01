# Diabetes - Post-Acute Care Pathway

## Objective
Improve blood glucose control in diabetic patients after hospital discharge. By optimizing post-discharge BG control, reduce length of hospital stay and reduce risk of hospital readmission, ER visits, and premature mortality in patients with labile blood glucose control, regardless of their primary cause of admission.

## Duration
**30 days** post-discharge

---

## Eligibility Criteria

### Inclusion
- Age 18-75
- Patient with known **diabetes (Type 1 or 2)** as primary diagnosis or comorbidity, eligible for outpatient monitoring
- Ability to **self-manage blood glucose** via frequent glucometer testing, dietary adjustments, and medication adjustments as needed
- Ability to **recognize early symptoms** of hypo and hyperglycemia
- Ability to complete tasks and questionnaires in-app and use required devices

---

## Primary Outcome Measures

| Outcome | Timeframe | Target |
|---------|-----------|--------|
| **30-Day Hospital Readmission** | 30 days | <15% |
| **30-Day Mortality** | 30 days | <3% |
| **90-Day Mortality** | 90 days | <5% |
| **6-Month Mortality** | 6 months | <8% |
| **HbA1c at Day 90** | 90 days | Improvement from baseline (goal individualized, typically <7.0%) |
| **Patient Satisfaction** | End of program | >85% satisfaction |

---

## Devices & Monitoring Equipment

See **[Devices Reference](../../shared/devices.md)** for complete specifications.

### Required Devices
- **Connected Glucometer** (ForaCare Test N Go)
  - Includes test strips, lancets, control solution
  - **CRITICAL**: Q6hrs glucose monitoring
- **Connected BP Cuff** (Welch Allyn 1700)
  - HTN common comorbidity with diabetes

---

## Daily Monitoring Protocol & Tasks

### Daily Tasks (Patient-Performed)

1. **Q6 Hourly BG Readings** - Categorized by Timing
   - **Fasting** (morning, before breakfast)
   - **Pre-meal** (before lunch, before dinner)
   - **Post-meal** (2 hours after each meal)
   - **Bedtime**

2. **Daily Food Diary** - Tracking Variations in Dietary Intake
   - Carbohydrate counting
   - Meal timing
   - Snacks

3. **Medication Adherence and Dose Tracking**
   - Insulin (basal and bolus doses)
   - Oral agents (metformin, sulfonylureas, SGLT2 inhibitors, GLP-1 agonists, others)

4. **Daily BP Measurement**
   - HTN coexists in >70% of diabetic patients

### Clinical Team Monitoring

#### Daily Diabetes Symptom Checker
See **[Diabetes Questionnaire](../../shared/questionnaires/diabetes-questionnaire.md)**
- Assessment for symptoms of **hyperglycemia** (thirst, polyuria, blurred vision, fatigue)
- Assessment for symptoms of **hypoglycemia** (sweating, shaking, confusion, palpitations)
- Contributing factors (illness, stress, dietary, activity, medication)
- Medication adherence

---

## Alert Thresholds & Escalations

See **[Universal Alert Thresholds](../../shared/alert-thresholds.md)** and **[Diabetes Comorbidities](../../shared/comorbidity-matrix.md#diabetes--hypertension)**.

### Diabetes-Specific Post-Acute Alerts

| Glucose Level | Interpretation | Action |
|---------------|----------------|--------|
| **≤2.8 mmol/L** (<50 mg/dL) | **Severe hypoglycemia** | **Immediate**: 15-15 rule, hold insulin, adjust regimen |
| **3.0-3.9 mmol/L** | Mild hypoglycemia | Treat per 15-15 rule, assess pattern |
| **4.0-10.0 mmol/L** | **TARGET RANGE** | Continue current regimen |
| **10.1-16.6 mmol/L** | Hyperglycemia | **Clinical call**: Adjust insulin/oral agents |
| **≥16.7 mmol/L** (≥300 mg/dL) | Severe hyperglycemia | **Urgent**: Check ketones, rule out DKA, insulin adjustment |
| **≥16.7 + N/V + confusion** | **Possible DKA/HHS** | **URGENT EVALUATION**: Hospital transfer if DKA confirmed |

---

## Complications & Adverse Events to Monitor

### Hyperglycemia, Hyperosmolar Coma and Associated Symptoms
- **Concern**: HHS (Type 2), severe dehydration, altered mental status
- **Action**: **Emergency evaluation** - glucose >33 mmol/L + confusion

### Hypoglycemia and Associated Symptoms
- **Concern**: Severe hypoglycemia → seizures, loss of consciousness, death
- **Action**: 15-15 rule, glucagon if unconscious, adjust insulin doses

### DKA (Type 1)
- **Concern**: Insulin deficiency → ketoacidosis
- **Action**: **Emergency evaluation** - glucose >13.9 mmol/L + ketones + N/V + abdominal pain

### Delayed Wound Healing
- **Concern**: Hyperglycemia impairs immune function and healing
- **Action**: Optimize glucose control, wound care referral

### Development of Hyperlipidemia, Hypertension, and Metabolic Syndrome
- **Concern**: Diabetes clusters with other metabolic diseases
- **Action**: Screen and treat per guidelines (statin, antihypertensives)

---

## Glucose Management Optimization

### Target Glucose Ranges
- **Fasting/Pre-meal**: 4.0-7.2 mmol/L (72-130 mg/dL)
- **Post-meal** (2 hrs): <10.0 mmol/L (<180 mg/dL)
- **Bedtime**: 5.0-8.3 mmol/L (90-150 mg/dL)
- **HbA1c Goal**: Typically <7.0% (individualize: <6.5% if low hypo risk, <8.0% if elderly/comorbidities)

### Insulin Regimens

#### Basal-Bolus (Physiologic, Preferred)
- **Basal**: Long-acting (glargine, detemir, degludec) once daily
- **Bolus**: Rapid-acting (lispro, aspart, glulisine) before meals
- **Dosing**: Total daily dose (TDD) = 0.5-1.0 units/kg
  - 50% basal, 50% bolus (divide among 3 meals)

#### Insulin Adjustment Rules
- **Pattern management**: Adjust insulin based on glucose patterns (not single values)
  - High fasting → Increase basal insulin
  - High post-meal → Increase meal insulin or reduce carbs
  - Low pre-meal → Reduce previous meal insulin OR add snack
- **Titration**: Adjust by 10-20% increments every 2-3 days

### Oral Antidiabetic Agents

#### Metformin (First-Line)
- **Dose**: 500-2000mg daily (start low, titrate up)
- **Benefits**: Lowers glucose, weight neutral, inexpensive
- **Side Effects**: GI upset (diarrhea, nausea) - take with food, start low dose
- **Contraindication**: eGFR <30 mL/min

#### SGLT2 Inhibitors
- **Examples**: Empagliflozin, dapagliflozin
- **Benefits**: Lower glucose + weight loss + CV benefits + renal protection
- **Side Effects**: Genital mycotic infections, euglycemic DKA (rare)

#### GLP-1 Receptor Agonists
- **Examples**: Semaglutide, liraglutide, dulaglutide
- **Benefits**: Lower glucose + weight loss + CV benefits
- **Side Effects**: Nausea (transient), pancreatitis (rare)
- **Administration**: Injectable (weekly or daily)

#### Sulfonylureas
- **Examples**: Glipizide, glyburide
- **Benefits**: Effective, inexpensive
- **Side Effects**: Hypoglycemia risk, weight gain

---

## Patient Education Content

### Diabetes Education Topics (Via Patient App)
- What is diabetes? (insulin resistance vs deficiency)
- Why glucose control matters (prevent complications: neuropathy, retinopathy, nephropathy, CV disease)
- **When to contact provider and signs of worsening hypo and hyperglycemia**
- Carbohydrate counting basics
- Hypoglycemia treatment (15-15 rule)
- Sick day management (increase monitoring, adjust insulin)
- Exercise and glucose (check before/after, may need snack or reduce insulin)

---

## Care Coordination & Escalation

### Care Team Monitoring
- **Patient questionnaire responses**: Hypo/hyper events, contributing factors
- **BG trends and physiologic parameters**: Pattern analysis (fasting highs, post-meal spikes, etc.)
- **Alerts**: Severe hypo/hyperglycemia

### Other Comorbidity Monitoring and Management
- **Diabetes + HTN**: ACE-I/ARB first-line, target BP <130/80
- **Diabetes + COPD**: Steroid courses worsen glucose - increase monitoring to Q4hrs during steroids

### Support and Intervention
- **Chat/Video**: Insulin dose adjustments, carb counting education, hypoglycemia management
- **Escalation**: Same-day clinical calls for severe hypo/hyperglycemia or DKA concern

---

## Other Recommended Care

### Diabetes Educator Virtual Consult
- **Recommended for all patients** post-discharge
- Topics: Insulin technique, carb counting, hypoglycemia management

### Dietician Virtual Consult (If Prescribed)
- Meal planning, portion control, carb counting advanced topics

### Labs - HbA1c (As Prescribed, at 3 Months)
- **HbA1c**: Reflects 3-month average glucose
- **Goal**: Typically <7.0% (individualized)
- **Trend**: Should improve from baseline if glucose control improved

---

## Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **No DKA/HHS episodes** | Primary safety goal | Monitor for symptoms, ketones |
| **Hypoglycemia events** | <2 per week (mild), 0 severe | Daily tracking |
| **Time in range** | >70% of glucose readings 4-10 mmol/L | Calculate from Q6hrs readings |
| **HbA1c improvement** | Decrease from baseline (goal <7.0%) | Measure at 3 months |
| **Medication adherence** | >80% | Daily tracking |

---

## References
- Source: Carepath Diabetes Post-Acute Care Pathway SOP
- American Diabetes Association (ADA) Standards of Care 2023
- Hypoglycemia Classification: International Hypoglycemia Study Group

**Related Skills**: If patient develops DKA/HHS or severe uncontrolled hyperglycemia, transition to `carepath-acute` skill for intensive insulin management.
