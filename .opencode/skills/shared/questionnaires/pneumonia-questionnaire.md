# Pneumonia Questionnaire

### Purpose
Daily symptom monitoring for patients with community-acquired pneumonia (CAP) during post-acute recovery phase. Detects worsening respiratory status, persistent fever, and treatment response.

### Administration Frequency
- **Acute Care**: Daily during hospital-at-home treatment
- **Post-Acute Care**: Daily for first 10-14 days, then as clinically indicated

---

## Pneumonia Daily Symptom Checker

| Question # | Question | Response Options |
|------------|----------|------------------|
| 1 | Did you fill your antibiotic prescription? | • Yes<br>• No |
| 2 | Are you still taking your antibiotics as prescribed? | • Yes<br>• No |
| 3 | Are you feeling better? | • Yes<br>• No |
| 4 | Are you experiencing any cough and/or any wheezing? | • Yes<br>• No |
| 5 | Have you noticed an increase in your coughing? | • Yes<br>• No |
| 6 | Has there been an increase in mucus and/or phlegm in the last 24 hours? | • Yes<br>• No |
| 7 | Have you seen a difference in the color of the mucus or phlegm in the last 24 hours? | • Yes<br>• No |
| 8 | *(If yes to Q7)* What is the color of the mucus and/or phlegm? | • Clear<br>• Yellow<br>• Green<br>• Brown |
| 9 | Were there any changes in your breathing since yesterday? | • No shortness of breath<br>• Some shortness of breath<br>• Still short of breath<br>• Increased shortness of breath<br>• Extreme shortness of breath |
| 10 | Were your activities affected by your breathing yesterday? | • I was able to do everything I wanted to do<br>• I was able to do most everything I wanted to do<br>• I wish I could have done more, but was unable<br>• I wasn't able to do what I wanted to do<br>• I could not get out of bed without help |

---

## Clinical Interpretation

### Treatment Adherence Monitoring

**Antibiotic Compliance** (Q1-2):
- **No to Q1** (didn't fill prescription):
  - Immediate intervention required
  - Address barriers: cost, pharmacy access, transportation
  - Risk of treatment failure and complications
- **No to Q2** (not taking as prescribed):
  - Assess reason: side effects, forgot, feeling better, cost
  - Reinforce importance of completing full course
  - Risk of antibiotic resistance and relapse

### Response to Treatment

**Positive Treatment Response Indicators**:
- Q3 = Yes (feeling better)
- Q9: Improving dyspnea (moving from "Extreme" → "Some")
- Q10: Increasing activity tolerance
- Q5-6: Decreasing cough and sputum production

**Treatment Failure Indicators**:
- Q3 = No after 48-72 hours of antibiotics
- Q9: Worsening or persistent severe dyspnea
- Q10: Unable to perform activities after 3-5 days of treatment
- Q5-7: Worsening productive cough with purulent sputum

### Sputum Assessment

**Sputum Color Interpretation** (Q7-8):
- **Clear**: Viral infection or resolving bacterial pneumonia
- **Yellow/Green**: Active bacterial infection, appropriate for antibiotic treatment
- **Brown**: Possible old blood, consider:
  - Pulmonary embolism (if sudden onset + dyspnea)
  - Necrotizing pneumonia
  - Underlying malignancy (smokers, elderly)

**Sputum Changes Over Time**:
- Yellow/green → clear: Good treatment response
- Clear → yellow/green: Possible secondary bacterial infection
- Any sputum → brown: Requires urgent clinical evaluation

### Respiratory Status

**Red Flag Respiratory Symptoms**:
- **Extreme shortness of breath** (Q9) at rest
- **Increased shortness of breath** (Q9) despite 48-72 hrs antibiotics
- **Unable to get out of bed** (Q10) without help
- New/worsening dyspnea after initial improvement (suggests complication)

**Complications to Consider**:
- **Parapneumonic effusion/empyema**: Persistent fever + dyspnea beyond day 5
- **Lung abscess**: Foul-smelling sputum, persistent fever, brown sputum
- **ARDS**: Rapidly worsening dyspnea + hypoxemia
- **Pulmonary embolism**: Sudden dyspnea worsening, pleuritic chest pain

### Correlation with Objective Data

**Temperature Monitoring**:
- Fever curve should trend downward by day 3-4 of antibiotics
- Persistent fever (>38.5°C) after 72 hours → Treatment failure or complication
- Defervescence followed by fever recurrence → Complication (effusion, abscess)

**SpO2 Monitoring**:
- Should improve with antibiotic treatment
- SpO2 <92% despite treatment → Consider:
  - Inadequate antibiotic coverage
  - Parapneumonic effusion
  - Pulmonary embolism
  - Underlying COPD/CHF exacerbation

**Activity Tolerance** (Q10):
- Should progressively improve day-by-day
- Stagnation or decline after 3-5 days → Reassess treatment

### Antibiotic Duration Guidance

**Treatment Response Timeline**:
- **24-48 hours**: Should see subjective improvement (feeling better)
- **48-72 hours**: Fever should begin to resolve
- **5-7 days**: Significant improvement in cough, dyspnea, activity tolerance
- **7-14 days**: Most symptoms resolved, completing antibiotic course

**Red Flags for Treatment Adjustment**:
- No improvement by 48-72 hours
- Clinical deterioration at any time
- New symptoms (chest pain, hemoptysis, confusion)

---

## Clinical Decision Support

### Early in Treatment (Days 1-3)

| Clinical Scenario | Interpretation | Action |
|-------------------|----------------|--------|
| Not filling prescription (Q1=No) | Treatment not initiated | **Urgent**: Call patient, arrange prescription pickup/delivery |
| Not taking antibiotics (Q2=No) | Non-adherence | **Same day**: Assess barriers, reinforce education |
| Worsening dyspnea (Q9 worse) | Treatment failure or complication | **Urgent**: Clinical assessment, consider imaging, antibiotic change |
| Brown sputum (Q8) | Potential hemorrhage/PE | **Urgent**: Clinical assessment, chest X-ray, consider CT/PE protocol |

### Mid-Treatment (Days 3-7)

| Clinical Scenario | Interpretation | Action |
|-------------------|----------------|--------|
| Still not feeling better (Q3=No) | Slow response or treatment failure | **Review**: Chest X-ray, labs (WBC, CRP), consider antibiotic adjustment |
| Persistent purulent sputum (Q8=Yellow/Green) | Ongoing infection | **Continue antibiotics**, reassess at day 7 |
| Improving dyspnea but persistent cough | Normal recovery pattern | **Continue treatment**, reassure patient |
| New/worsening symptoms | Complication | **Reassess**: Imaging, labs, consider specialist consultation |

### Late Treatment (Days 7-14)

| Clinical Scenario | Interpretation | Action |
|-------------------|----------------|--------|
| Much improved, minimal symptoms | Good treatment response | **Complete antibiotic course**, transition to follow-up |
| Persistent symptoms | Complicated pneumonia or comorbidity | **Extend monitoring**, consider pulmonary referral |
| Relapse after improvement | Possible resistant organism or complication | **Urgent reassessment**: Culture, imaging, ID consultation |

---

## Documentation Template

```
Pneumonia Symptom Check - Day [X] of Treatment

Antibiotic Adherence: [Compliant / Non-compliant]
Overall Status: [Improving / Stable / Worsening]

Respiratory Symptoms:
- Dyspnea: [Level from Q9]
- Cough: [Increasing / Stable / Decreasing]
- Sputum: [Color] - [Increasing / Stable / Decreasing]
- Activity tolerance: [Level from Q10]

Objective Data:
- Temperature: [X]°C
- SpO2: [X]% on [room air / O2]
- Respiratory rate: [X]

Assessment: [Clinical interpretation]
Plan: [Continue current treatment / Adjust antibiotics / Urgent evaluation]
```

---

## References

- CURB-65 and SMRT-CO scoring for pneumonia severity (used in acute eligibility criteria, not in questionnaire)
- CAP treatment guidelines: Infectious Diseases Society of America / American Thoracic Society
- Expected treatment response timelines: Mandell LA, et al. IDSA/ATS Consensus Guidelines. Clin Infect Dis. 2007.

---

**Clinical Note**: Pneumonia treatment response is highly variable. Patient-reported symptoms (this questionnaire) should always be correlated with vital signs (SpO2, temperature, respiratory rate) and objective measures (chest X-ray, labs) for complete clinical picture.
