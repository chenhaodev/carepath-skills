# Carepath OpenCode Skills

**Clinical decision support skills for remote patient monitoring across 7 acute and post-acute disease pathways.**

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-Apache%202.0-green)
![OpenCode](https://img.shields.io/badge/OpenCode-compatible-purple)
![Qwen-Pro](https://img.shields.io/badge/Qwen--Pro-optimized-orange)

---

## 📋 Overview

Carepath Skills provide comprehensive clinical protocols for **hospital-at-home acute care** and **post-discharge readmission prevention** across 7 common disease pathways:

- **CHF** (Congestive Heart Failure)
- **COPD** (Chronic Obstructive Pulmonary Disease)
- **Pneumonia** (Community-Acquired Pneumonia)
- **HTN** (Hypertension / Hypertensive Urgency)
- **Diabetes** (DKA/HHS)
- **DVT** (Deep Vein Thrombosis)
- **COVID-19**

### What This Repository Contains

**2 OpenCode Agent-Skills**:

1. **`carepath-acute`** - Acute care protocols (hospital-at-home with IV therapy, 2-10 days)
2. **`carepath-postacute`** - Post-acute care protocols (readmission prevention, 14-90 days)

**For each disease, you get**:
- Evidence-based treatment protocols
- Device selection guidance (continuous monitors, vital sign devices, lab equipment)
- Alert thresholds with 3-tier escalation (Critical/Urgent/Advisory)
- Daily patient task checklists
- Complication surveillance and management
- Transition criteria between care levels

**Plus shared resources**:
- 7 disease-specific daily questionnaires with scoring/interpretation
- Universal vital sign alert thresholds table
- Monitoring device catalog with specifications
- Comorbidity interaction matrix (how multiple diseases affect protocols)

---

## ✨ Features

### Designed for AI Agents (Qwen-Pro + OpenCode)

- **Structured Markdown**: Clear headings, tables, and sections for optimal LLM parsing
- **Progressive Disclosure**: Quick-reference tables → detailed protocols → specialized references
- **Explicit Formats**: Step-by-step instructions, decision trees, checklists
- **Cross-References**: Internal links between related protocols (acute ↔ post-acute, disease ↔ comorbidity)

### Evidence-Based Clinical Content

- Sourced from official clinical guidelines:
  - ACC/AHA Heart Failure Guidelines 2022
  - GOLD COPD Guidelines 2023
  - IDSA/ATS Pneumonia Guidelines
  - AHA/ACC Hypertension Guidelines 2017
  - ADA Standards of Diabetes Care 2024
  - ACCP Antithrombotic Therapy Guidelines
  - NIH COVID-19 Treatment Guidelines
- Includes clinical pearls, red flags, and quality metrics

### Comprehensive Coverage

- **7 acute care pathways** with IV treatment protocols
- **7 post-acute care pathways** with readmission prevention strategies
- **7 daily questionnaires** with clinical interpretation
- **Bidirectional transition protocols** (acute ↔ post-acute handoff procedures)
- **Comorbidity matrix** (25+ disease combinations with protocol modifications)

---

## 🚀 Installation

### Prerequisites

- **OpenCode CLI** - [Installation Guide](https://github.com/OpenCodeDev/opencode)
- **Qwen-Pro API Access** (recommended for optimal performance, but works with other LLM providers)

### Install Carepath Skills

1. **Clone this repository**:

```bash
git clone https://github.com/YOUR-USERNAME/carepath-skills.git
cd carepath-skills
```

2. **Copy skills to OpenCode skills directory**:

```bash
# For macOS/Linux:
cp -r .opencode/skills/carepath-acute ~/.opencode/skills/
cp -r .opencode/skills/carepath-postacute ~/.opencode/skills/
cp -r .opencode/skills/shared ~/.opencode/skills/

# For Windows:
xcopy /E /I .opencode\skills\carepath-acute %USERPROFILE%\.opencode\skills\carepath-acute
xcopy /E /I .opencode\skills\carepath-postacute %USERPROFILE%\.opencode\skills\carepath-postacute
xcopy /E /I .opencode\skills\shared %USERPROFILE%\.opencode\skills\shared
```

3. **Verify installation**:

```bash
opencode list-skills
```

You should see:
- `carepath-acute`
- `carepath-postacute`

---

## 📖 Usage

### Invocation Methods

**Method 1: Contextual Auto-Load** (Recommended)

OpenCode automatically loads the appropriate skill when you mention trigger keywords in your query:

```
# Acute care triggers:
"I need help with a CHF patient requiring IV diuresis"
"COPD exacerbation protocol for hospital at home"
"COVID patient needs acute care monitoring"

# Post-acute triggers:
"Patient discharged yesterday with CHF, how to monitor for readmission?"
"Post-discharge pneumonia monitoring protocol"
"30-day CHF readmission prevention"
```

**Method 2: Explicit Slash Command**

```
/carepath-acute [your query]
/carepath-postacute [your query]
```

### Example Queries

**Acute Care Examples**:

```
"68 year old female with CHF exacerbation requiring IV furosemide. 
Set up hospital-at-home acute care protocol."

→ Returns: CHF acute care eligibility criteria, device requirements 
(weight scale, BP cuff, VitalPatch), IV diuretic protocol, daily 
monitoring tasks, alert thresholds, transition criteria.
```

```
"COPD patient with acute exacerbation, purulent sputum, oxygen 
requirement 4L NC. What's the treatment protocol?"

→ Returns: COPD acute care protocol including corticosteroids 
(prednisone 40mg x 5 days), bronchodilators, antibiotic indications, 
oxygen titration target (SpO2 88-92%), monitoring duration (3-7 days).
```

**Post-Acute Care Examples**:

```
"CHF patient discharged 2 days ago, how do I monitor for readmission 
in the next 30 days?"

→ Returns: CHF post-acute pathway with daily weight monitoring 
(#1 readmission predictor), KCCQ-12 quality of life assessment, 
alert thresholds (weight gain ≥3 lbs/3 days), GDMT optimization plan.
```

```
"Diabetes patient post-DKA discharge. How long to monitor glucose 
and what are the alert thresholds?"

→ Returns: Diabetes post-acute protocol (30 days), QID glucose 
checks (or CGM), ketone monitoring if glucose >250 mg/dL, 
alert thresholds (glucose <70 or >250 mg/dL), sick day management, 
recurrent DKA prevention.
```

**Comorbidity Example**:

```
"COPD patient with recent pneumonia and CHF. Discharged yesterday. 
What's the monitoring protocol?"

→ Returns: Primary pathway selection (COPD post-acute - 90 days 
due to high re-exacerbation rate), plus CHF comorbidity modifications 
(add daily weights, lower threshold for dyspnea escalation, BNP useful 
for CHF vs COPD differentiation).
```

---

## 📁 Repository Structure

```
carepath-skills/
├── README.md                          # This file
├── LICENSE                            # Apache 2.0 license
├── CONTRIBUTING.md                    # Contribution guidelines
├── Carepath-Prod.pdf                  # Source SOPs (reference)
├── Carepath-Prod.txt                  # Extracted text from PDF
├── .opencode/
│   └── skills/
│       ├── carepath-acute/            # Acute care skill
│       │   ├── SKILL.md              # Main skill file (invocation, usage guide)
│       │   ├── references/           # Disease protocols (7 files)
│       │   │   ├── chf-acute.md
│       │   │   ├── copd-acute.md
│       │   │   ├── pneumonia-acute.md
│       │   │   ├── htn-acute.md
│       │   │   ├── diabetes-acute.md
│       │   │   ├── dvt-acute.md
│       │   │   ├── covid-acute.md
│       │   │   └── transition-to-postacute.md
│       │   └── assets/
│       │       └── qa-scenarios-acute.md
│       │
│       ├── carepath-postacute/        # Post-acute care skill
│       │   ├── SKILL.md              # Main skill file
│       │   ├── references/           # Disease protocols (7 files)
│       │   │   ├── chf-postacute.md
│       │   │   ├── copd-postacute.md
│       │   │   ├── pneumonia-postacute.md
│       │   │   ├── htn-postacute.md
│       │   │   ├── diabetes-postacute.md
│       │   │   ├── dvt-postacute.md
│       │   │   ├── covid-postacute.md
│       │   │   └── transition-from-acute.md
│       │   └── assets/
│       │       └── qa-scenarios-postacute.md
│       │
│       └── shared/                    # Shared resources
│           ├── alert-thresholds.md    # Universal vital sign thresholds
│           ├── devices.md             # Monitoring device catalog
│           ├── comorbidity-matrix.md  # Cross-disease interactions
│           └── questionnaires/        # Daily symptom questionnaires
│               ├── chf-questionnaire.md
│               ├── copd-questionnaire.md
│               ├── pneumonia-questionnaire.md
│               ├── htn-questionnaire.md
│               ├── diabetes-questionnaire.md
│               ├── dvt-questionnaire.md
│               └── covid-questionnaire.md
```

---

## 🎯 Disease Coverage

### Acute Care Pathways (Hospital-at-Home)

| Disease | Duration | Key Treatment | Primary Outcome |
|---------|----------|---------------|-----------------|
| **CHF** | 2-10 days | IV diuresis (furosemide, bumetanide, torsemide) | Euvolemia, 30-day readmission <20% |
| **COPD** | 3-7 days | Corticosteroids, bronchodilators, antibiotics (if purulent sputum) | Symptom improvement, prevent respiratory failure |
| **Pneumonia** | 5-10 days | IV antibiotics (ceftriaxone + azithromycin or fluoroquinolone) | Afebrile, clinical improvement, 30-day mortality <5% |
| **HTN** | 1-3 days | IV antihypertensives (labetalol, nicardipine, hydralazine) | BP controlled <160/100, prevent end-organ damage |
| **Diabetes** | 2-5 days | IV insulin + fluids (DKA/HHS protocol) | DKA/HHS resolution, prevent recurrence |
| **DVT** | 3-7 days | IV heparin → oral anticoagulation (warfarin or DOAC) | Therapeutic anticoagulation, prevent PE |
| **COVID-19** | 2-6 days | IV remdesivir, dexamethasone, oxygen support | Prevent progression, 30-day mortality <1% |

### Post-Acute Care Pathways (Readmission Prevention)

| Disease | Duration | Key Monitoring | Primary Outcome |
|---------|----------|----------------|-----------------|
| **CHF** | 30 days | Daily weights, KCCQ-12 QoL, GDMT optimization | 30-day readmission <20% (national ~25%) |
| **COPD** | 90 days | CAT score, SpO2 trends, exacerbation action plan | Re-exacerbation <50% (national ~50% in 90 days) |
| **Pneumonia** | 30 days | Temperature, respiratory symptoms, relapse surveillance | Relapse <10%, full recovery |
| **HTN** | 30 days | Twice daily BP, medication adherence, lifestyle modifications | BP controlled <130/80, adherence >80% |
| **Diabetes** | 30 days | QID glucose (or CGM), ketone monitoring, insulin adherence | Recurrent DKA <20%, glucose control improved |
| **DVT** | 90 days | INR (if warfarin), PE symptom surveillance, bleeding surveillance | No PE, no major bleeding, adherence >80% |
| **COVID-19** | 14 days | Twice daily temp, SpO2 trends, long COVID screening | Prevent deterioration (days 5-10), detect long COVID |

---

## 🩺 Clinical Features

### Alert Thresholds (3-Tier Escalation)

All pathways use a standardized 3-tier alert system:

| Alert Level | Response Time | Typical Triggers | Action |
|-------------|---------------|------------------|--------|
| 🔴 **Critical** | <5 min (acute) <br> <1 hr (post-acute) | Life-threatening: SpO2 <92%, severe dyspnea, chest pain, confusion, glucose <70 mg/dL | Immediate physician notification, possible 911 call or ED referral |
| 🟠 **Urgent** | <1 hr (acute) <br> <24 hrs (post-acute) | High risk: Weight gain ≥3 lbs/3 days (CHF), CAT ≥20 (COPD), fever >38°C (Pneumonia) | Same-day intervention (medication adjustment, video visit, closer monitoring) |
| 🟡 **Advisory** | <4 hrs (acute) <br> <2-3 days (post-acute) | Early warning: Trending weight gain, mild hyperglycemia, medication non-adherence | Patient education, reminder, routine follow-up |

### Questionnaires with Scoring

All 7 questionnaires include:
- **Daily symptom assessment** (disease-specific)
- **Validated scoring** (KCCQ-12 for CHF, CAT for COPD, etc.)
- **Clinical interpretation** (when to escalate, what scores mean)
- **Emergency criteria** (911 triggers - e.g., COVID blue lips, DVT chest pain for PE)

**Example (CHF)**:
- KCCQ-12 score 0-100 (higher = better quality of life)
- Score drop ≥10 points = significant QoL deterioration, readmission risk
- Orthopnea question: "How many pillows do you sleep on?" (increase = worsening heart failure)

### Comorbidity Matrix

Handles complex patients with multiple diseases:

**Example: CHF + COPD Patient**
- **Dyspnea differentiation**: Both cause dyspnea - use BNP (elevated in CHF, normal in COPD alone) and response to diuretics (CHF improves, COPD doesn't)
- **Medication conflicts**: Beta-blockers beneficial for CHF, but caution in COPD (may worsen bronchospasm → use cardioselective beta-blockers like metoprolol, bisoprolol)
- **Alert thresholds**: SpO2 target 88-92% (COPD target) instead of >95% (general target)
- **Monitoring**: Both daily weights (CHF) AND CAT score (COPD)

**25+ comorbidity combinations documented**, including:
- CHF + Diabetes, COPD + Pneumonia, HTN + Diabetes, DVT + COVID, etc.

### Transition Protocols

**Bidirectional care level transitions**:

1. **Acute → Post-Acute** (Step-Down):
   - Criteria: IV therapy complete, clinical stability, no complications
   - Process: Device changes (VitalPatch → Everion armband), alert threshold adjustment, care team handoff
   - Example: CHF patient euvolemic after 5 days IV diuresis → transition to 30-day post-acute monitoring

2. **Post-Acute → Acute** (Escalation):
   - Criteria: Requires IV therapy, deterioration despite outpatient management
   - Process: Root cause analysis, urgent evaluation, re-enter acute care pathway
   - Example: CHF patient with 5-lb weight gain over 3 days, worsening dyspnea → re-admit for IV diuresis

---

## 🛠️ Configuration for Qwen-Pro

These skills are optimized for Qwen-Pro's strengths:

1. **Structured Tables**: Qwen-Pro excels at parsing and reasoning over tabular data (used extensively for device specs, alert thresholds, comorbidity interactions)

2. **Step-by-Step Instructions**: Clear numbered steps for protocols (treatment algorithms, transition checklists, escalation workflows)

3. **Explicit Formats**: Decision trees, checklists, templates (reduces hallucination, improves consistency)

4. **Cross-References**: Internal links allow progressive disclosure (quick reference → detailed protocol → specialized knowledge)

**Recommended OpenCode Configuration**:

```yaml
# In your .opencode/config.yml
skills:
  carepath-acute:
    enabled: true
    auto_load: true  # Auto-load when acute care keywords detected
  
  carepath-postacute:
    enabled: true
    auto_load: true  # Auto-load when post-acute keywords detected

models:
  default: qwen-pro  # Optimized for this model, but works with others
```

---

## 📊 Use Cases

### 1. Hospital-at-Home Program Setup

**Scenario**: Healthcare system launching hospital-at-home service for CHF patients

**How Carepath Skills Help**:
- **CHF acute care protocol** provides evidence-based IV diuresis guidelines, device requirements, monitoring tasks
- **Alert thresholds** define when to escalate (weight gain ≥2 lbs/day = immediate diuretic adjustment)
- **Transition criteria** specify when patient can step down to post-acute care (euvolemia achieved, on oral diuretics)
- **Quality metrics** track program success (30-day readmission rate, length of stay, patient satisfaction)

**Query Example**:
```
"We're setting up a CHF hospital-at-home program. What devices do we need, 
what are the alert thresholds, and how do we know when to discharge patients 
to post-acute care?"
```

---

### 2. Post-Discharge Readmission Prevention

**Scenario**: Primary care practice wants to reduce 30-day readmissions for recently discharged patients

**How Carepath Skills Help**:
- **Post-acute care protocols** provide 30-day (CHF, Pneumonia, HTN, Diabetes) or 90-day (COPD, DVT) monitoring guidelines
- **Daily questionnaires** detect early decompensation (KCCQ-12 score drop in CHF, CAT score increase in COPD)
- **Medication adherence tracking** addresses #1 cause of readmissions (non-adherence)
- **Transition protocols** ensure smooth handoff from hospital to home monitoring

**Query Example**:
```
"Patient discharged 3 days ago after CHF exacerbation. How do I monitor 
for readmission signs? What are the key parameters to watch?"
```

---

### 3. Comorbidity Management

**Scenario**: Patient with CHF + COPD + Diabetes admitted for CHF exacerbation

**How Carepath Skills Help**:
- **Primary pathway selection**: CHF acute care (primary diagnosis)
- **Comorbidity matrix**: Modifications for COPD (SpO2 target 88-92%) and Diabetes (glucose monitoring during diuresis + corticosteroid use)
- **Medication interactions**: Beta-blocker caution (CHF benefit vs COPD risk), corticosteroid hyperglycemia (diabetes worsening)
- **Alert thresholds**: Adjusted for baseline (COPD SpO2 90% = normal, not alert)

**Query Example**:
```
"Patient with CHF, COPD, and diabetes admitted for CHF exacerbation. 
What monitoring modifications do I need for the COPD and diabetes?"
```

---

### 4. Clinical Decision Support for Non-Specialists

**Scenario**: General practice physician managing complex patients remotely

**How Carepath Skills Help**:
- **Evidence-based protocols** provide specialist-level guidance (cardiology for CHF, pulmonology for COPD, etc.)
- **Red flags** specify when to escalate to specialist or ED (CHF patient with weight gain despite maximal diuresis → cardiology consult for ultrafiltration)
- **Treatment algorithms** guide medication selection and dosing (CHF GDMT optimization, COPD exacerbation antibiotics)
- **Clinical pearls** highlight nuances (COVID silent hypoxemia, CHF vs COPD dyspnea differentiation)

**Query Example**:
```
"I'm a family doctor managing a COPD patient remotely. Patient reports 
increased dyspnea and yellow sputum. Do I start antibiotics? Which one?"
```

---

### 5. Quality Improvement & Benchmarking

**Scenario**: Healthcare organization tracking remote monitoring program performance

**How Carepath Skills Help**:
- **Quality metrics** defined for each pathway (30-day readmission rate, mortality, patient satisfaction, medication adherence)
- **National benchmarks** provided (CHF readmission national ~25%, target <20%)
- **Transition success metrics** track premature discharges (7-day readmission rate <5%)
- **Alert response time tracking** ensures patient safety (critical alerts responded to within 1 hour)

**Query Example**:
```
"What are the key quality metrics for our CHF post-acute program? 
What benchmarks should we target?"
```

---

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:

- How to report issues
- How to suggest protocol improvements
- How to add new disease pathways
- Coding standards for OpenCode skills
- Testing and validation procedures

**Areas We'd Love Help With**:
- Additional disease pathways (stroke, ACS, sepsis, CKD, liver disease, etc.)
- International guideline variations (European, Asian, etc.)
- Pediatric adaptations (current protocols are adult-focused)
- Translation to other languages
- Integration with specific EMR systems

---

## 📄 License

This project is licensed under the **Apache License 2.0** - see [LICENSE](LICENSE) file for details.

**What this means**:
- ✅ Free to use commercially
- ✅ Free to modify and distribute
- ✅ Patent grant included
- ✅ No warranty (use at your own risk)
- ⚠️ Must include original license and copyright notice
- ⚠️ Changes must be documented

**Clinical Use Disclaimer**:
These skills provide clinical decision support based on published guidelines. They are NOT a substitute for professional medical judgment. Always verify recommendations against your local protocols, institutional guidelines, and individual patient circumstances. Users assume all responsibility for clinical decisions.

---

## 📞 Support & Contact

- **Issues**: [GitHub Issues](https://github.com/YOUR-USERNAME/carepath-skills/issues)
- **Discussions**: [GitHub Discussions](https://github.com/YOUR-USERNAME/carepath-skills/discussions)
- **Email**: [your-email@example.com]

**OpenCode Community**:
- [OpenCode Documentation](https://opencode.dev/docs)
- [OpenCode Discord](https://discord.gg/opencode)

---

## 🙏 Acknowledgments

**Clinical Content Sources**:
- American College of Cardiology (ACC) / American Heart Association (AHA)
- Global Initiative for Chronic Obstructive Lung Disease (GOLD)
- Infectious Diseases Society of America (IDSA) / American Thoracic Society (ATS)
- American Diabetes Association (ADA)
- American College of Chest Physicians (ACCP)
- National Institutes of Health (NIH)
- Centers for Disease Control and Prevention (CDC)

**Technology**:
- OpenCode framework by [OpenCodeDev]
- Qwen-Pro by Alibaba Cloud

**Inspiration**:
- Carepath-Prod.pdf source document (original clinical SOPs)
- Hospital-at-home pioneers (Johns Hopkins, Mount Sinai, Brigham and Women's)
- Care Transitions Intervention (CTI) model
- Project RED (Re-Engineered Discharge)

---

## 🔄 Version History

### v1.0.0 (2026-02-01)
- ✨ Initial release
- 📋 7 acute care disease pathways
- 📋 7 post-acute care disease pathways
- 📝 7 daily questionnaires with scoring
- 🔗 Bidirectional transition protocols
- 📊 Comorbidity matrix (25+ combinations)
- 📱 Universal alert thresholds
- 🩺 Device catalog with specifications

---

## 📚 Additional Resources

**Related Projects**:
- [OpenCode Skills Repository](https://github.com/OpenCodeDev/skills)
- [Medical Prompt Engineering Guide](https://github.com/example/medical-prompts)

**Clinical Guidelines** (used as source material):
- [ACC/AHA Heart Failure Guidelines 2022](https://www.ahajournals.org/hf/guidelines)
- [GOLD COPD Guidelines 2023](https://goldcopd.org/2023-gold-report/)
- [IDSA/ATS Pneumonia Guidelines](https://www.idsociety.org/cap-guidelines)
- [ADA Standards of Diabetes Care 2024](https://diabetesjournals.org/care/issue/47/Supplement_1)
- [NIH COVID-19 Treatment Guidelines](https://www.covid19treatmentguidelines.nih.gov/)

**Training Materials**:
- See `examples/` directory for sample queries and responses
- See `assets/qa-scenarios-*.md` for test cases

---

**Made with ❤️ for healthcare AI**

*Improving patient outcomes through structured clinical decision support for remote monitoring programs.*
