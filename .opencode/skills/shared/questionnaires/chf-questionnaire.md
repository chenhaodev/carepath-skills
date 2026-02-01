# Heart Failure (CHF) Questionnaires

This document contains two questionnaires used for CHF remote patient monitoring:
1. **Daily Heart Failure Symptom Checker** - Daily assessment for acute symptoms
2. **KCCQ-12** (Kansas City Cardiomyopathy Questionnaire) - Monthly quality of life assessment with scoring

---

## 1. Daily Heart Failure Symptom Checker

### Purpose
Assess daily symptoms of volume overload, activity limitations, and cardiac decompensation.

### Questionnaire

| Question # | Question | Response Options |
|------------|----------|------------------|
| 1 | Were there any changes in your breathing yesterday? | • No shortness of breath<br>• Some shortness of breath<br>• Short of breath<br>• Increased shortness of breath<br>• Extreme shortness of breath |
| 2 | Were your activities affected by your breathing yesterday? | • I was able to do everything I wanted to do<br>• I was able to do most everything I wanted to do<br>• I wish I could have done more, but was unable<br>• I wasn't able to do what I wanted to do<br>• I could not get out of bed without help |
| 3 | Did you use a chair or additional pillows to sleep last night? | • Yes<br>• No |
| 4 | Did you encounter shortness of breath first thing in the morning? | • Yes<br>• No |
| 5 | Did you notice any swelling in your hands, lower legs, or feet yesterday? | • Yes<br>• No |
| 6 | Since yesterday, did you experience dizziness or lightheadedness? | • Yes<br>• No |

### Clinical Interpretation

**Red Flag Symptoms** (require immediate clinical review):
- Extreme shortness of breath at rest
- Unable to get out of bed without help (Question 2, option 5)
- New orthopnea (Question 3 = Yes) combined with other symptoms
- Worsening dyspnea trend over 2-3 days

**Volume Overload Indicators**:
- Progressive shortness of breath (Questions 1-2)
- New/worsening peripheral edema (Question 5)
- Orthopnea requiring extra pillows/chair sleeping (Question 3)
- Paroxysmal nocturnal dyspnea (Question 4)

**Medication Side Effects**:
- Dizziness/lightheadedness (Question 6) may indicate over-diuresis or hypotension

**Correlation with Vitals**:
- Cross-reference with weight trends (daily weight gain >0.9kg)
- Check SpO2 readings if breathing changes reported
- Review BP if dizziness reported

---

## 2. KCCQ-12 (Kansas City Cardiomyopathy Questionnaire)

### Purpose
Monthly assessment of heart failure-specific quality of life and functional status. Used to track disease progression and treatment response.

### Administration Frequency
- **Post-Acute Care**: Monthly (Day 0, Day 30)
- **Acute Care**: Not typically administered during acute phase

### Questionnaire

The KCCQ-12 consists of 12 questions across 4 domains:

#### Domain 1: Physical Limitation (Questions 1-6)
*"Over the past 2 weeks, how much has your heart failure limited your ability to do the following?"*

Response scale for Q1-6:
- **1** = Extremely limited
- **2** = Quite a bit limited
- **3** = Moderately limited
- **4** = Slightly limited
- **5** = Not at all limited
- **6** = Limited for other reasons or did not do the activity

| Q# | Activity |
|----|----------|
| 1 | Showering/bathing |
| 2 | Walking 1 block on level ground |
| 3 | Hurrying or jogging (as if to catch a bus) |
| 4 | Climbing a flight of stairs without stopping |
| 5 | Doing yardwork, housework, or carrying groceries |
| 6 | Going places away from home |

#### Domain 2: Symptom Frequency (Questions 7-9)
*"Over the past 2 weeks, how many times did you have..."*

Response scale for Q7-9:
- **1** = All of the time
- **2** = Several times per day
- **3** = At least once a day
- **4** = 3 or more times per week but not every day
- **5** = 1-2 times per week
- **6** = Less than once a week
- **7** = Never over the past 2 weeks

| Q# | Symptom |
|----|---------|
| 7 | Swelling in your feet, ankles, or legs when you woke up in the morning? |
| 8 | Felt tired, fatigued, or low on energy? |
| 9 | Been forced to sleep sitting up in a chair or with at least 3 pillows to prop you up because of shortness of breath? |

#### Domain 3: Quality of Life (Questions 10-11)
| Q# | Question | Response Options |
|----|----------|------------------|
| 10 | Over the past 2 weeks, how much has your heart failure limited your enjoyment of life? | **1** = It has extremely limited my enjoyment of life<br>**2** = It has limited my enjoyment of life quite a bit<br>**3** = It has moderately limited my enjoyment of life<br>**4** = It has slightly limited my enjoyment of life<br>**5** = It has not limited my enjoyment of life |
| 11 | If you had to spend the rest of your life with your heart failure the way it is right now, how would you feel about this? | **1** = Not at all satisfied<br>**2** = Mostly dissatisfied<br>**3** = Somewhat satisfied<br>**4** = Mostly satisfied<br>**5** = Completely satisfied |

#### Domain 4: Social Limitation (Question 12)
| Q# | Question | Response Options |
|----|----------|------------------|
| 12 | Over the past 2 weeks, how much has your heart failure affected your lifestyle? | **1** = It has extremely affected my lifestyle<br>**2** = It has affected my lifestyle quite a bit<br>**3** = It has moderately affected my lifestyle<br>**4** = It has slightly affected my lifestyle<br>**5** = It has not affected my lifestyle |

### KCCQ-12 Scoring Algorithm

#### Step 1: Score Individual Domains

**Physical Limitation Score (PLS)**:
```
PLS = [(Sum of Q1-6) - 6] / 24 × 100
```
- Exclude items marked "6" (limited for other reasons) from numerator and adjust denominator

**Symptom Frequency Score (SFS)**:
```
SFS = [(Sum of Q7-9) - 3] / 18 × 100
```

**Quality of Life Score (QLS)**:
```
QLS = [(Sum of Q10-11) - 2] / 8 × 100
```

**Social Limitation Score (SLS)**:
```
SLS = [(Q12 score) - 1] / 4 × 100
```

#### Step 2: Calculate Summary Scores

**Overall Summary Score (OSS)**:
```
OSS = (PLS + SFS + QLS + SLS) / 4
```

**Clinical Summary Score (CSS)**:
```
CSS = (PLS + SFS) / 2
```

### Score Interpretation

| Score Range | Health Status | Clinical Meaning |
|-------------|---------------|------------------|
| **75-100** | Excellent | Minimal HF impact on quality of life |
| **50-74** | Good | Moderate HF symptoms, manageable |
| **25-49** | Fair | Significant HF burden, frequent symptoms |
| **0-24** | Poor | Severe HF impact, severely limited |

### Clinically Important Changes

- **5-point change**: Minimally clinically important difference (MCID)
- **≥10-point decline**: Significant worsening, consider intervention adjustment
- **≥10-point improvement**: Meaningful clinical improvement

### Clinical Use Cases

**Trending Over Time**:
- Compare scores monthly to detect gradual decline or improvement
- Persistent decline (>10 points over 1-2 months) warrants medication optimization

**Treatment Response**:
- Measure KCCQ-12 before and 30 days after medication changes
- Goal: Improve score by ≥5 points

**Readmission Risk**:
- KCCQ-12 score <50 associated with higher 30-day readmission risk
- Scores <25 indicate very high-risk patients requiring intensive monitoring

**Correlate with Objective Data**:
- Low scores despite "good" vitals may indicate medication intolerance, depression, or non-HF comorbidities
- High scores with objective worsening (weight gain, SpO2 drops) may indicate poor symptom awareness

---

## References

- Daily Symptom Checker: Adapted from Biofourmis HF Symptom Checker
- KCCQ-12: Green CP, et al. Development and evaluation of the Kansas City Cardiomyopathy Questionnaire. J Am Coll Cardiol. 2000.
- Scoring: Official KCCQ scoring guidelines, cv-outcomes.org

---

**Clinical Note**: Questionnaires supplement objective vitals monitoring. Always correlate subjective symptoms with weight trends, vital signs, and medication adherence before making clinical decisions.
