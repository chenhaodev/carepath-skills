# COPD (Chronic Obstructive Pulmonary Disease) Questionnaires

This document contains two questionnaires used for COPD remote patient monitoring:
1. **Daily COPD Symptom Checker** - Daily assessment for exacerbation symptoms
2. **COPD Assessment Test (CAT)** - Bi-monthly disease impact assessment with scoring

---

## 1. Daily COPD Symptom Checker

### Purpose
Monitor daily respiratory symptoms and detect early signs of COPD exacerbation.

### Questionnaire

| Question # | Question | Response Options |
|------------|----------|------------------|
| 1 | Were there any changes in your breathing yesterday? | • No shortness of breath<br>• Some shortness of breath<br>• Short of breath<br>• Increased shortness of breath<br>• Extreme shortness of breath |
| 2 | Did you experience any issues with your breathing yesterday while completing activities? | • No shortness of breath<br>• Some shortness of breath<br>• Short of breath<br>• Increased shortness of breath<br>• Extreme shortness of breath |
| 3 | Was your activity level affected by your breathing yesterday? | • I was able to do everything I wanted to do<br>• I did most everything I wanted to do<br>• I wish I could have done more<br>• I had trouble doing most activities<br>• I couldn't do anything I wanted to do |
| 4 | In the past 24 hours, have you experienced a fever? | • No<br>• Yes - Less than 37.2°C<br>• Yes - 37.2 to 38.9°C<br>• Yes - 39 to 40°C<br>• Yes - Greater than 40°C<br>• Did not take temperature – I just feel warm |
| 5 | Are you experiencing any cough and/or any wheezing? | • Yes<br>• No |
| 6 | Have you noticed an increase in your coughing? | • Yes<br>• No |
| 7 | Has there been an increase in mucus and/or phlegm in the last 24 hours? | • Yes<br>• No |
| 8 | Have you seen a difference in the color of the mucus or phlegm in the last 24 hours? | • Yes<br>• No |
| 9 | *(If yes to Q8)* What is the color of the mucus and/or phlegm? | • Clear<br>• Yellow<br>• Green<br>• Brown |
| 10 | Have you been using your daily maintenance inhaler as prescribed? | • Yes<br>• No |
| 11 | *(If no to Q10)* What is the reason for not taking your daily maintenance inhaler? | • I didn't remember to use it<br>• Other reasons *(free text)* |
| 12 | Did you use your rescue inhaler in the last 24 hours? | • Yes<br>• No |

### Clinical Interpretation

**COPD Exacerbation Indicators** (Anthonisen Criteria):
- **Major symptoms** (2+ present suggests exacerbation):
  1. Increased dyspnea (Q1-2: "Increased" or "Extreme")
  2. Increased sputum volume (Q7: Yes)
  3. Increased sputum purulence (Q8-9: Yellow or Green)

**Red Flag Symptoms**:
- Fever ≥38.9°C (Q4) + respiratory symptoms
- Extreme shortness of breath at rest (Q1-2)
- Inability to perform daily activities (Q3: options 4-5)
- Increased rescue inhaler use without improvement

**Medication Adherence**:
- Missing maintenance inhaler (Q10-11): Address barriers
- Increased rescue inhaler use (Q12): May indicate inadequate control

**Sputum Monitoring**:
- Green/yellow sputum (Q9) may indicate bacterial infection requiring antibiotics
- Brown sputum may indicate old blood (consider PE, infection, or cancer)
- Increased volume + purulence = classic exacerbation sign

**Correlate with Vitals**:
- SpO2 trends with respiratory symptoms
- Respiratory rate elevation
- Temperature if fever reported

---

## 2. COPD Assessment Test (CAT)

### Purpose
Bi-monthly comprehensive assessment of COPD impact on daily life and wellbeing. Quantifies disease burden.

### Administration Frequency
- **Post-Acute Care**: Bi-monthly (Day 0, Day 14, Day 30)
- **Acute Care**: At admission and discharge to track exacerbation recovery

### Questionnaire

The CAT consists of 8 items scored on a 0-5 scale. For each question, select the number that best describes your condition.

| Q# | Dimension | 0 (Best) | 1 | 2 | 3 | 4 | 5 (Worst) |
|----|-----------|----------|---|---|---|---|-----------|
| 1 | **Cough** | I never cough | | | | | I cough all the time |
| 2 | **Phlegm** | I have no phlegm (mucus) in my chest at all | | | | | My chest is completely full of phlegm (mucus) |
| 3 | **Chest tightness** | My chest does not feel tight at all | | | | | My chest feels very tight |
| 4 | **Breathlessness** | When I walk up a hill or one flight of stairs I am not breathless | | | | | When I walk up a hill or one flight of stairs I am very breathless |
| 5 | **Activity limitation** | I am not limited doing any activities at home | | | | | I am very limited doing activities at home |
| 6 | **Confidence** | I am confident leaving my home despite my lung condition | | | | | I am not at all confident leaving my home because of my lung condition |
| 7 | **Sleep** | I sleep soundly | | | | | I don't sleep soundly because of my lung condition |
| 8 | **Energy** | I have lots of energy | | | | | I have no energy at all |

### CAT Scoring Algorithm

#### Total Score Calculation
```
CAT Score = Sum of all 8 items (Q1 + Q2 + Q3 + Q4 + Q5 + Q6 + Q7 + Q8)
```

**Score Range**: 0-40

### Score Interpretation

| CAT Score | Impact Level | Clinical Meaning |
|-----------|--------------|------------------|
| **0-10** | Low | Mild COPD impact; symptoms well controlled |
| **11-20** | Medium | Moderate COPD impact; noticeable daily limitations |
| **21-30** | High | Severe COPD impact; significantly affects daily life |
| **31-40** | Very High | Extremely severe impact; major life disruption |

### Clinically Important Changes

- **2-point change**: Minimally clinically important difference (MCID)
- **≥3-point increase**: Clinically significant worsening
- **≥3-point decrease**: Clinically meaningful improvement

### Clinical Use Cases

**Exacerbation Detection**:
- Sudden increase ≥3 points from baseline suggests acute exacerbation
- Compare current score to patient's stable baseline

**Treatment Optimization**:
- Persistent CAT score >20 despite treatment → Consider:
  - Pulmonary rehabilitation referral
  - Medication escalation (LABA/LAMA, ICS)
  - Home oxygen assessment
  - Specialist referral

**Recovery Monitoring**:
- Post-exacerbation: Track CAT every 2 weeks
- Goal: Return to within 2 points of pre-exacerbation baseline
- Persistent elevation suggests incomplete recovery

**Risk Stratification**:
- CAT ≥10 associated with increased exacerbation risk
- CAT ≥18 predicts higher mortality and readmission rates

**Domain-Specific Insights**:
- High cough/phlegm scores (Q1-2) → Mucolytic therapy
- High breathlessness score (Q4) → Assess for pulmonary rehab, oxygen
- Poor sleep/low confidence (Q6-7) → Screen for anxiety/depression
- Low energy (Q8) → Rule out anemia, thyroid, cardiac causes

### Correlation with Other Assessments

**CAT vs Daily Symptom Checker**:
- Daily checker captures acute changes
- CAT captures overall disease burden trend
- Rising CAT score despite stable daily symptoms → Gradual decline

**CAT vs Spirometry**:
- CAT correlates moderately with FEV1 (r = -0.3 to -0.5)
- Low CAT with poor spirometry → Patient may underreport symptoms
- High CAT with preserved FEV1 → Consider comorbidities (cardiac, deconditioning)

**CAT vs Exacerbation Frequency**:
- Patients with CAT ≥20 have 2-3x higher exacerbation rates
- Use CAT to identify high-risk patients for intensive monitoring

### Score Documentation

**Recommended Format**:
```
CAT Score: 18/40 (Medium Impact)
Breakdown:
- Cough/Phlegm (Q1-2): 6/10 (high)
- Breathlessness (Q4): 3/5 (moderate)
- Activity/Confidence (Q5-6): 5/10 (moderate)
- Sleep/Energy (Q7-8): 4/10 (moderate)

Interpretation: Moderate COPD burden with prominent mucus symptoms.
Recommendation: Consider mucolytic therapy; continue current bronchodilators.
```

---

## References

- Daily COPD Questionnaire: Adapted from Biofourmis COPD Symptom Checker
- COPD Assessment Test (CAT): Jones PW, et al. Development and first validation of the COPD Assessment Test. Eur Respir J. 2009.
- Official CAT scoring: catestonline.org
- Anthonisen Criteria: Anthonisen NR, et al. Antibiotic therapy in exacerbations of chronic obstructive pulmonary disease. Ann Intern Med. 1987.

---

**Clinical Note**: CAT is a patient-reported outcome measure (PROM). High scores indicate patient perception of disease burden, which may differ from objective measures like FEV1. Both subjective and objective assessments are important for comprehensive COPD management.
