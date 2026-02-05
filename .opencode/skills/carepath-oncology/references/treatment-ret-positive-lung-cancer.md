# RET Fusion-Positive Non-Small Cell Lung Cancer - Treatment Pathway

**Version**: 1.0  
**Last Updated**: 2026-02-05  
**Sources**: NCCN Guidelines v3.2025, ESMO 2024, LIBRETTO-001/431 Trials, ARROW Trial

---

## Objective

Provide evidence-based first-line treatment protocol for **RET fusion-positive metastatic non-small cell lung cancer (NSCLC)**. This pathway guides targeted therapy selection, monitoring, adverse event management, and response assessment.

**Key Principle**: RET fusion-positive NSCLC is driven by oncogene addiction. First-line targeted therapy with RET inhibitors is the standard of care, not chemotherapy.

---

## Epidemiology & Biomarker

### RET Fusion Background

| Parameter | Details |
|-----------|---------|
| **Frequency** | 1-2% of all NSCLC |
| **Demographics** | Slightly more common in younger, never-smokers, adenocarcinoma histology |
| **Co-mutations** | Generally low tumor mutational burden; rarely co-occurs with other actionable drivers (EGFR, ALK) |
| **Prognosis** | Historically poor with chemotherapy; excellent response to RET inhibitors |

### Biomarker Testing

**Required Before Treatment**:
- **NGS Panel**: Essential (RNA-based NGS preferred for fusion detection)
- **IHC**: NOT recommended (poor sensitivity/specificity for RET)
- **Tissue**: Prefer tissue; liquid biopsy acceptable if tissue unavailable

**If RET-negative on initial testing**:
- Confirm with orthogonal method (RNA-seq if IHC was initial test)
- Consider re-biopsy if clinical suspicion high

---

## First-Line Treatment Options

### Recommended Regimens

| Rank | Agent | Brand | Dose | Administration | Evidence |
|------|-------|-------|------|-----------------|-----------|
| **1** | **Selpercatinib** | Retevmo | 160mg twice daily | Oral | LIBRETTO-001/LIBRETTO-431 |
| **2** | **Pralsetinib** | Gavreto | 400mg once daily | Oral | ARROW Trial |

### Drug Comparison

| Feature | Selpercatinib | Pralsetinib |
|---------|---------------|-------------|
| **Dosing** | 160mg BID | 400mg QD |
| **CNS Activity** | Excellent | Excellent |
| **ORR (Treatment-Naive)** | ~85% | ~78% |
| **Median PFS** | ~22 months | ~24 months |
| **Common AEs** | Hypertension, diarrhea, dry mouth | Hypertension, anemia, constipation |
| **Drug Interactions** | CYP3A4 substrate | CYP3A4 substrate |
| **Food Effect** | Take with or without food | Take on empty stomach |

### Selection Factors

**Choose Selpercatinib if**:
- Patient has difficulty with twice-daily dosing
- History of poor adherence to medications
- Drug interaction concerns with Pralsetinib

**Choose Pralsetinib if**:
- Preference for once-daily dosing
- History of hypertension (similar rates but may prefer one over other based on tolerability)

**Both are NCCN Category 1 preferred regimens** - choice based on availability, cost, physician preference, and patient factors.

---

## Treatment Protocol

### Baseline Assessment (Before Starting)

| Assessment | Details |
|------------|---------|
| **History & Physical** | Complete exam, performance status, weight |
| **CBC with Differential** | Baseline hemoglobin, WBC, platelets |
| **Comprehensive Metabolic Panel** | Liver function (ALT, AST, bilirubin), renal function (creatinine) |
| **Thyroid Function** | TSH, free T4 (RET inhibitors can cause hypothyroidism) |
| **ECG** | Baseline QTc (both drugs can prolong QT) |
| **Blood Pressure** | Establish baseline (hypertension is common AE) |
| **Imaging** | CT chest/abdomen/pelvis or PET-CT (response assessment baseline) |
| **Brain MRI** | Baseline brain metastases screening (both drugs have excellent CNS activity but need baseline) |
| **Symptom Assessment** | Using [`oncology-questionnaire.md`](../../shared/questionnaires/oncology-questionnaire.md) |

### Dose & Administration

**Selpercatinib**:
- **Starting Dose**: 160mg orally twice daily
- **With or without food**: Consistent administration
- **Swallow whole**: Do not crush, chew, or open capsules
- **Missed dose**: If missed, take at next scheduled time (do not double)

**Pralsetinib**:
- **Starting Dose**: 400mg orally once daily
- **Empty stomach**: Take at least 1 hour before or 2 hours after food
- **Swallow whole**: Do not crush, chew, or open capsules
- **Missed dose**: If missed, take at next scheduled time (do not double)

### Dose Modifications for Toxicity

| Toxicity | Grade 1 | Grade 2 | Grade 3 | Grade 4 |
|----------|---------|---------|---------|---------|
| **Hypertension** | Continue; monitor | Continue; add antihypertensive | Hold until ≤Grade 1; reduce dose 40% | Discontinue |
| **Diarrhea** | Continue; loperamide PRN | Continue; loperamide scheduled | Hold until ≤Grade 1; reduce dose 40% | Discontinue |
| **Dry Mouth** | Continue; symptomatic care | Continue; symptomatic care | Hold until ≤Grade 1; reduce dose 40% | Discontinue |
| **ALT/AST Elevation** | Continue; monitor LFTs | Continue; monitor LFTs 2x weekly | Hold until ≤Grade 1; reduce dose 40% | Discontinue |
| **QTc Prolongation** | Continue; monitor ECG | Hold until ≤Grade 1; correct electrolytes | Discontinue |
| **Pneumonitis** | Continue; monitor | Hold; steroids if symptomatic | Hold; steroids; consider dose reduction | Discontinue |

**Dose Reduction Levels**:
- **Selpercatinib**: 120mg BID → 80mg BID → 40mg BID
- **Pralsetinib**: 300mg QD → 200mg QD → 100mg QD

---

## Monitoring Schedule

### Follow-Up Timeline

| Timepoint | Assessments |
|-----------|-------------|
| **Week 2** | BP check, symptom review (phone/telehealth) |
| **Week 4** | CBC, CMP, TSH, BP, symptom assessment |
| **Week 8** | CBC, CMP, TSH, BP, imaging (CT chest/abdomen) |
| **Every 8-12 weeks** | Imaging (CT), symptom assessment |
| **Every 3 months** | CBC, CMP, TSH (ongoing) |
| **As needed** | ECG if QTc concerns |

### Response Assessment

| Response | Criteria (RECIST 1.1) |
|----------|----------------------|
| **Complete Response (CR)** | Disappearance of all target lesions |
| **Partial Response (PR)** | ≥30% decrease in sum of diameters |
| **Stable Disease (SD)** | Neither PR nor PD criteria met |
| **Progressive Disease (PD)** | ≥20% increase in sum of diameters OR new lesions |

**Timeline**:
- First response assessment: **8 weeks**
- Subsequent: Every **8-12 weeks** if stable
- Continue treatment until progression or unacceptable toxicity

---

## Adverse Event Management

### Common AEs by System

| System | Adverse Event | Frequency | CTCAE Grade | Management |
|--------|---------------|-----------|-------------|------------|
| **Vascular** | Hypertension | 30-40% | Grade 1-3 | See [`symptom-hypertension.md`](symptom-hypertension.md); start antihypertensive (ACEi/ARB preferred); target BP <140/90 |
| **Gastrointestinal** | Diarrhea | 50-60% | Grade 1-3 | Loperamide 2mg PRN; hydrate; see [`symptom-diarrhea.md`](symptom-diarrhea.md) |
| **Gastrointestinal** | Dry Mouth | 40-50% | Grade 1-2 | Saliva substitutes; good oral hygiene; see [`symptom-mucositis.md`](symptom-mucositis.md) |
| **Gastrointestinal** | Constipation | 20-30% | Grade 1-2 | See [`symptom-constipation.md`](symptom-constipation.md); stool softeners prophylactically |
| **Hematologic** | Anemia | 20-30% | Grade 1-3 | Iron studies; EPO if symptomatic; transfusion if <7g/dL |
| **Hepatic** | ALT/AST Elevation | 15-20% | Grade 1-3 | Monitor LFTs 2x weekly if Grade 2; see [`symptom-liver.md`](symptom-liver.md) |
| **Cardiac** | QTc Prolongation | 5-10% | Grade 1-3 | ECG baseline and periodic; correct electrolytes (K+, Mg2+); avoid other QT-prolonging drugs |
| **Pulmonary** | Pneumonitis | 3-5% | Grade 2-3 | Hold drug; prednisone 1mg/kg; see [`symptom-dyspnea.md`](symptom-dyspnea.md) |
| **Endocrine** | Hypothyroidism | 10-15% | Grade 1-2 | TSH every 6-8 weeks; levothyroxine replacement |
| **Musculoskeletal** | Arthralgia | 15-20% | Grade 1-2 | NSAIDs or acetaminophen; physical therapy |
| **General** | Fatigue | 30-40% | Grade 1-3 | See [`symptom-fatigue.md`](symptom-fatigue.md); exercise, treat anemia, optimize sleep |

### Critical AEs Requiring Immediate Action

| AE | Threshold | Action |
|----|-----------|--------|
| **Severe Hypersensitivity** | Grade 3-4 | Discontinue; epinephrine; steroids |
| **Severe Pneumonitis** | Grade 3-4 | Discontinue; high-dose steroids; ICU if needed |
| **Hepatic Failure** | Grade 4 ALT/AST | Discontinue; hepatology consult |
| **Severe QTc Prolongation** | QTc >500ms or Δ>60ms | Discontinue; cardiology consult |
| **Arterial Thrombosis** | Any grade | Discontinue; anticoagulation; vascular consult |

---

## Symptom Pathway Cross-References

This treatment pathway integrates with symptom pathways for adverse event management:

| Adverse Event | Symptom Pathway | Reference |
|---------------|-----------------|-----------|
| Diarrhea | Chemotherapy-Induced Diarrhea | [`symptom-diarrhea.md`](symptom-diarrhea.md) |
| Constipation | Opioid-Induced Constipation | [`symptom-constipation.md`](symptom-constipation.md) |
| Mucositis/Dry Mouth | Oral Mucositis | [`symptom-mucositis.md`](symptom-mucositis.md) |
| Fatigue | Cancer-Related Fatigue | [`symptom-fatigue.md`](symptom-fatigue.md) |
| Pain | Cancer Pain | [`symptom-pain.md`](symptom-pain.md) |
| Dyspnea | Dyspnea Management | [`symptom-dyspnea.md`](symptom-dyspnea.md) |
| Skin Rash | Skin Toxicity | [`symptom-skin-rash.md`](symptom-skin-rash.md) |
| Neuropathy | CIPN | [`symptom-neuropathy.md`](symptom-neuropathy.md) |
| Distress | Psychosocial Distress | [`symptom-distress.md`](symptom-distress.md) |
| Hypertension | Blood Pressure Management | [`symptom-hypertension.md`](symptom-hypertension.md) |

---

## Drug Interactions

### Major Interactions

| Drug | Interaction | Management |
|------|-------------|------------|
| **Ketoconazole, Itraconazole** (CYP3A4 inhibitors) | ↑ Selpercatinib/Pralsetinib levels | Avoid combination; if unavoidable, reduce RET inhibitor dose by 50% |
| **Rifampin, Carbamazepine** (CYP3A4 inducers) | ↓ Selpercatinib/Pralsetinib levels | Avoid combination |
| **Proton Pump Inhibitors** | ↓ Pralsetinib absorption | Take Pralsetinib 2 hours before or after PPI |
| **QTc-prolonging drugs** (Amiodarone, Sotalol) | Additive QTc prolongation | Avoid combination; if necessary, frequent ECG monitoring |
| **Antacids** (Pralsetinib) | ↓ Absorption | Take Pralsetinib 2 hours before or 2 hours after antacids |

### Common Drug Interactions in Cancer Patients

| Drug Class | Example | Interaction |
|------------|---------|-------------|
| **Antiemetics** | Ondansetron | QTc prolongation (additive) |
| **Antiemetics** | Aprepitant | CYP3A4 inhibition (↑ RET inhibitor levels) |
| **Antifungals** | Fluconazole | CYP3A4 inhibition |
| **Antidepressants** | Escitalopram | QTc prolongation |
| **Steroids** | Dexamethasone | CYP3A4 induction (↓ RET inhibitor levels) |

---

## Resistance Mechanisms & Second-Line

### Acquired Resistance

**Mechanisms**:
1. **On-target**: Secondary RET mutations (V804 gatekeeper mutations)
2. **Off-target**: Activation of bypass tracks (MET amplification, KRAS mutations)
3. **Histologic transformation**: Small cell lung cancer transformation (rare)

### Second-Line Options

| Scenario | Recommended Option |
|----------|-------------------|
| **Progression with RET solvent front mutation** | Clinical trial; next-generation RET inhibitors |
| **Progression with MET amplification** | Selpercatinib + MET inhibitor (clinical trial) |
| **Progression - no targetable mutation** | Chemotherapy (pemetrexed + platinum ± bevacizumab) |
| **Progression - PD-L1 high (≥50%)** | Immunotherapy (pembrolizumab) ± chemotherapy |
| **Oligoprogression** | Local therapy (SBRT) + continue RET inhibitor |

---

## Special Populations

### Elderly (≥75 years)

- Start at standard dose (both drugs well-tolerated)
- Close monitoring for hypertension and fatigue
- More frequent LFT and BP monitoring
- Consider drug interaction review (polypharmacy)

### Hepatic Impairment

| Child-Pugh Class | Selpercatinib | Pralsetinib |
|------------------|---------------|-------------|
| **Mild (A)** | No adjustment | No adjustment |
| **Moderate (B)** | Reduce to 120mg BID | Reduce to 200mg QD |
| **Severe (C)** | Not studied | Not recommended |

### Renal Impairment

- No dose adjustment for mild-moderate renal impairment
- No data for severe renal impairment (CrCl <30 mL/min)

### Pregnancy & Lactation

- **Pregnancy**: Contraindicated (teratogenic in animal studies)
- **Contraception**: Effective contraception during treatment and for 1 month after (females), 3 months after (males)
- **Lactation**: Discontinue breastfeeding during treatment and for 1 week after last dose

---

## Patient Education Points

### What to Tell Patients

1. **Take medication consistently** - Same time each day, with/without food as directed
2. **Report symptoms early** - Don't wait for symptoms to become severe
3. **BP monitoring** - Check BP weekly at home; report readings >140/90
4. **Signs of liver problems** - Yellowing skin/eyes, dark urine, right upper quadrant pain
5. **Signs of lung problems** - New cough, shortness of breath, fever
6. **Avoid certain medications** - Tell all doctors/pharmacists you're on RET inhibitor
7. **Contraception** - Effective birth control during treatment
8. **Missed dose** - Don't double up; take at next scheduled time

### Warning Signs (Call Immediately)

- Severe headache, vision changes (possible hypertension emergency)
- Shortness of breath, difficulty breathing
- Yellowing of skin or eyes
- Severe diarrhea with dehydration signs (dizziness, dark urine)
- Chest pain or palpitations

---

## Quality Metrics

| Metric | Target |
|--------|--------|
| **Time to Treatment** | ≤14 days from biomarker confirmation to treatment start |
| **Treatment Adherence** | ≥90% of prescribed doses taken |
| **Hospitalization Rate** | <15% within first 3 months (excluding planned admissions) |
| **Response Rate (ORR)** | ≥70% (treatment-naive) |
| **Time to Response** | ≤8 weeks |
| **Grade 3-4 AE Rate** | <25% |
| **Treatment Discontinuation due to AE** | <10% |

---

## Transition Criteria

### Continue Current Therapy If:
- Partial response or stable disease
- No Grade 3-4 toxicities (or manageable with dose reduction)
- Patient tolerating treatment

### Consider Treatment Break If:
- Patient requests treatment holiday (quality of life)
- Significant but reversible toxicity
- Planning for surgery (hold 1 week before and after)

### Discontinue If:
- Progressive disease (unless clinical benefit continues)
- Grade 4 toxicity or Grade 3 toxicity recurring despite dose reduction
- Patient refuses further treatment

---

## References

**Primary Guidelines**:
- NCCN Guidelines: Non-Small Cell Lung Cancer, Version 3.2025
- ESMO Clinical Practice Guidelines: Metastatic NSCLC, 2024
- ASCO Guidelines: Molecular Testing in Lung Cancer, 2024

**Clinical Trials**:
- LIBRETTO-001: Selpercatinib in RET fusion-positive NSCLC (Drilon et al., NEJM 2020, updated 2023)
- LIBRETTO-431: Selpercatinib vs. chemo/bevacizumab in treatment-naive RET+ NSCLC (WCLC 2023)
- ARROW: Pralsetinib in RET fusion-positive NSCLC (Gainor et al., Lancet Oncol 2021, updated 2024)

**Other Resources**:
- FDA Prescribing Information: Retevmo (Selpercatinib), Gavreto (Pralsetinib)
- CTCAE v5.0: Common Terminology Criteria for Adverse Events
- RECIST 1.1: Response Evaluation Criteria in Solid Tumors

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| **1.0** | 2026-02-05 | Initial release |

---

*This pathway is intended for oncology healthcare professionals. Always refer to local protocols, institutional guidelines, and the most current prescribing information.*
