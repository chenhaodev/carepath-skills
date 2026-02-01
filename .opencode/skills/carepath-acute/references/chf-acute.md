# CHF (Congestive Heart Failure) - Acute Care Pathway

## Objective
Enable physiologic monitoring and geographically-distributed care coordination to ensure effective acute care for patients with a CHF exacerbation requiring IV diuresis in a hospital-at-home setting.

## Duration
**2-10 days** (typical 3-7 days)

---

## Eligibility Criteria

### Inclusion
- Clinical or diagnostic evidence of CHF exacerbation requiring **IV diuresis**
- Hemodynamically stable (no vasopressor requirement)
- No severe respiratory distress (can maintain SpO2 >90% on ≤4L NC)

### Exclusion Criteria
- **GWTG-HF Risk Score >10%** in-hospital mortality
- **Class IV / Stage D heart failure**
- **LVAD** (left ventricular assist device)
- **Inotropic support** (acute) or vasopressor requirement
- **Severe pulmonary hypertension**
- **O2 requirement >4L nasal cannula** to maintain SpO2 >90%

---

## Primary Outcome Measures

| Outcome | Timeframe | Target |
|---------|-----------|--------|
| **30-Day ED Presentation** | 30 days post-discharge | Minimize unplanned ED visits |
| **30-Day Readmission** | 30 days post-discharge | <20% (national benchmark ~25%) |
| **30-Day Mortality** | 30 days post-discharge | <5% |
| **Patient Satisfaction Score** | End of program | >85% satisfaction |
| **Disease-Specific PROMs** | Throughout care | Track symptom burden, QoL |

---

## Devices & Monitoring Equipment

See **[Devices Reference](../../shared/devices.md)** for detailed specifications.

### Required Devices
- **Connected Weight Scale**
  - Welch Allyn RPM-SCALE100 OR ForaCare W550
  - **Critical**: Daily weight is #1 CHF monitoring parameter
- **Connected BP Cuff**
  - Welch Allyn 1700 OR Omron BP7000
  - Monitor for hypo/hypertension with diuretic adjustments

### Optional Devices (based on severity and clinician preference)
- **Continuous Telemetry** (VitalConnect VitalPatch)*
  - HR, RR, skin temp, ECG, arrhythmia detection, fall detection
  - Use for higher-risk patients or those with arrhythmia history
- **Connected Pulse Oximeter** (Nonin 3230)*
  - For patients with respiratory symptoms or hypoxia concerns

*Denotes optional device per SOP

---

## Daily Monitoring Protocol

### Clinical Team Reviews (Daily)
1. **Physiologic Data Review**
   - Weight trend (daily weight gain/loss)
   - BP trends (orthostatic drops with diuresis?)
   - Heart rate/rhythm (if on continuous telemetry)
   - SpO2 (if monitored)

2. **Subjective Patient Data Review**
   - **Daily Symptom Diary**: See **[CHF Questionnaire](../../shared/questionnaires/chf-questionnaire.md)**
     - Breathing changes (dyspnea, orthopnea)
     - Activity tolerance
     - Edema presence/progression
     - Dizziness (over-diuresis warning)

3. **Patient Task Compliance Review**
   - Daily weight recorded?
   - BP measurements completed?
   - Medications taken as prescribed?
   - Fluid/salt intake tracking adherence

---

## Alert Thresholds & Escalations

See **[Universal Alert Thresholds](../../shared/alert-thresholds.md)** for complete threshold table.

### CHF-Specific Critical Alerts

| Parameter | Threshold | Clinical Significance | Action |
|-----------|-----------|----------------------|--------|
| **Weight Gain** | >0.9 kg/day OR >2.3 kg/week | Fluid retention, inadequate diuresis | **Same-day evaluation**: Increase diuretic dose |
| **SpO2** | <92% | Pulmonary edema, respiratory compromise | **Urgent**: Assess for flash APE, increase O2, escalate diuretics |
| **Systolic BP** | <90 mmHg | Hypotension from over-diuresis or cardiogenic shock | **Hold diuretics**, assess volume status, clinical evaluation |
| **Systolic BP** | ≥180 mmHg | Severe HTN increasing afterload | **Same-day**: Add/increase vasodilator therapy |
| **Heart Rate** | <55 or >120 bpm | Bradycardia (beta-blocker) or tachycardia (decompensation) | **Review medications**, rhythm assessment if on telemetry |
| **Arrhythmia** (if on telemetry) | AFib with RVR, VTach, frequent PVCs | Arrhythmia-mediated cardiomyopathy | **Urgent cardiology evaluation** |

### Symptom-Based Alerts
- **Orthopnea** (new or worsening): Suggests volume overload
- **Paroxysmal Nocturnal Dyspnea**: Severe volume overload
- **Extreme SOB** at rest: Flash pulmonary edema - **EMERGENT**
- **Dizziness + BP <90**: Over-diuresis - hold diuretics

**Alert Escalation**: Clinical teams define their own escalation protocols based on organizational resources.

---

## Care Coordination

### Telemedicine/Virtual Visits
- **Daily check-ins** during first 48-72 hours (critical diuresis period)
- **Every 2-3 days** thereafter if stable
- **Ad-hoc visits** for alert review, medication adjustments

### Interdisciplinary Task Management
- **Phlebotomy**: Home blood draws for BMP, BNP monitoring (every 2-3 days)
- **Radiology**: Portable chest X-ray if worsening dyspnea
- **IV Diuretic Administration**: Home health RN visits for IV furosemide/bumetanide
- **Medication Delivery**: Coordinate refills, dose adjustments

---

## Treatment Protocol

### IV Diuresis Strategy
1. **Initial Dose**: Based on home oral dose (typically 2-2.5x oral dose IV)
   - Example: If on furosemide 40mg PO daily → Start 80-100mg IV daily
2. **Titration**: Based on weight response and urine output
   - Goal: 0.5-1.0 kg weight loss per day
   - Urine output goal: 1-2 L negative daily
3. **Transition to Oral**: Once euvolemic (back to dry weight + symptom improvement)
   - Typically day 3-7 of treatment
   - Oral dose usually 1.5-2x IV dose

### Monitoring During Diuresis
- **Daily weights**: Most important parameter
- **BMP every 2-3 days**: Monitor for:
  - Hypokalemia (<3.5 mmol/L) → Supplement potassium
  - Hyponatremia (<135 mmol/L) → Consider fluid restriction
  - Worsening renal function (Cr increase >26.5 μmol/L) → May need to reduce diuretic rate
- **BNP/NT-proBNP** (optional): Trend to assess treatment response

---

## Complications to Monitor

### Volume Overload Signs (Under-Diuresed)
- Progressive weight gain
- Worsening dyspnea
- Increasing peripheral edema
- SpO2 decline
- **Action**: Increase diuretic dose, consider adding thiazide (diuretic synergy)

### Over-Diuresis Signs
- Hypotension (SBP <90)
- Dizziness, lightheadedness
- Worsening renal function (Cr rise)
- Hypokalemia
- **Action**: Hold/reduce diuretics, assess volume status, replete electrolytes

### Cardiorenal Syndrome
- Worsening renal function despite diuresis
- Difficult to diurese (poor urine output)
- **Management**: Consider ultrafiltration, nephrology consult

---

## Comorbidity Management

See **[Comorbidity Matrix](../../shared/comorbidity-matrix.md)** for detailed guidance.

### Common CHF Comorbidities
- **CHF + Diabetes**: Monitor glucose (diuretics worsen hyperglycemia), consider SGLT2i
- **CHF + HTN**: BP control critical, ACE-I/ARB + beta-blocker cornerstone
- **CHF + COPD**: Differentiate dyspnea etiology (crackles vs wheezes), manage both
- **CHF + CKD**: Diuretic resistance common, may need higher doses

---

## Transition to Post-Acute Care

### Discharge Readiness Criteria
- ✅ Weight at or near dry weight (stable ≥2 days)
- ✅ Dyspnea improved to baseline or mild residual
- ✅ Transitioned to oral diuretics
- ✅ No supplemental O2 requirement (or back to baseline)
- ✅ Hemodynamically stable (SBP >90, HR 50-100)
- ✅ BMP stable (no worsening renal function, K >3.5)

### Handoff to Post-Acute
See **[Transition to Post-Acute](./transition-to-postacute.md)** for full protocol.

**Key Handoff Information**:
- Dry weight achieved
- Diuretic regimen (dose, frequency)
- Medication changes during acute care
- KCCQ-12 baseline for post-acute trending
- Follow-up appointments scheduled (cardiology, PCP)

---

## References
- Source: Carepath CHF Acute Care Pathway SOP
- GWTG-HF Risk Score: Get With The Guidelines - Heart Failure
- ACC/AHA Heart Failure Guidelines 2022
- Diuretic strategies: DOSE Trial (NEJM 2011)

**Related Skills**: After stabilization, patient transitions to `carepath-postacute` skill for 30-day readmission prevention monitoring.
