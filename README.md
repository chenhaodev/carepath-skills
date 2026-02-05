# Carepath OpenCode Skills v2.0

**Clinical decision support skills for remote patient monitoring across oncology symptom pathways and 7 acute/post-acute disease pathways.**

![Version](https://img.shields.io/badge/version-2.0.0-blue)
![License](https://img.shields.io/badge/license-Apache%202.0-green)
![OpenCode](https://img.shields.io/badge/OpenCode-compatible-purple)
![Qwen-Pro](https://img.shields.io/badge/Qwen--Pro-optimized-orange)

---

## 📋 Overview

Carepath Skills provide comprehensive clinical protocols for **hospital-at-home acute care**, **post-discharge readmission prevention**, and **oncology symptom management**:

### Disease Pathways (7 pathways)
- **CHF** (Congestive Heart Failure)
- **COPD** (Chronic Obstructive Pulmonary Disease)
- **Pneumonia** (Community-Acquired Pneumonia)
- **HTN** (Hypertension / Hypertensive Urgency)
- **Diabetes** (DKA/HHS)
- **DVT** (Deep Vein Thrombosis)
- **COVID-19**

### Oncology Pathways (NEW in v2.0)
- **18 Symptom Management Pathways** (Fever, Pain, Nausea, Fatigue, Neuropathy, Distress, etc.)
- **Cancer-Type Specific Treatment Pathways** (RET+ Lung Cancer, with more coming)
- **CTCAE v5.0 Grading** for toxicity assessment
- **Evidence-Based Supportive Care** (NCCN, ASCO, ESMO guidelines)

---

## ✨ What's New in v2.0

| Feature | Description |
|---------|-------------|
| 🆕 **carepath-oncology Skill** | 18 symptom pathways + cancer treatment pathways |
| 🆕 **RET+ Lung Cancer Pathway** | First-line targeted therapy (Selpercatinib, Pralsetinib) |
| 🆕 **CTCAE Grading** | Standardized toxicity grading for all oncology symptoms |
| 🆕 **QA Scenarios** | 4 realistic oncology test cases |
| 🆕 **Enhanced Shared Resources** | Oncology-specific alert thresholds, nurse protocols, comorbidity matrix |

---

## 🚀 Quick Start

### Installation

```bash
# Clone repository
git clone https://github.com/chenhaodev/carepath-skills.git
cd carepath-skills

# Copy all skills to OpenCode
cp -r .opencode/skills/* ~/.opencode/skills/

# Verify installation
opencode list-skills
```

### Available Skills
```
carepath-acute       # Hospital-at-home protocols (7 disease pathways)
carepath-postacute   # Post-discharge readmission prevention
carepath-oncology    # Oncology symptom + treatment pathways ⭐ NEW
shared               # Shared resources (questionnaires, alerts, devices)
```

---

## 📖 Usage Examples

### Oncology Examples

```
# Symptom management
"Patient on chemotherapy reports fever of 38.5°C. What do I do?"
→ Returns: Febrile neutropenia protocol, immediate ED referral

"Managing diarrhea in patient on immunotherapy. What's the protocol?"
→ Returns: Immunotherapy colitis grading, CTCAE criteria, steroid management

# Treatment pathway
"I have a newly diagnosed RET+ lung cancer patient. What's first-line treatment?"
→ Returns: Selpercatinib 160mg BID OR Pralsetinib 400mg QD, monitoring schedule

"Uncontrolled pain in cancer patient. How do I assess and manage?"
→ Returns: WHO Analgesic Ladder, CTCAE pain grading, opioid conversion
```

### Acute/Post-Acute Examples

```
# Acute care
"CHF patient requires IV diuresis at home. Set up protocol."
→ Returns: IV furosemide protocol, daily weights, alert thresholds

# Post-acute care
"CHF patient discharged. How to prevent 30-day readmission?"
→ Returns: Daily weight monitoring, KCCQ-12, GDMT optimization
```

---

## 📁 Repository Structure

```
carepath-skills/
├── README.md
├── RELEASE.md                    # Release notes ⭐ NEW
├── LICENSE
├── .opencode/
│   └── skills/
│       ├── carepath-acute/              # 7 disease pathways
│       ├── carepath-postacute/          # 7 disease pathways
│       ├── carepath-oncology/           # ⭐ NEW in v2.0
│       │   ├── SKILL.md                # Main entry point
│       │   ├── references/
│       │   │   ├── symptom-*.md        # 18 symptom pathways
│       │   │   └── treatment-*.md       # Cancer treatment pathways
│       │   └── assets/
│       │       └── qa-scenarios-oncology.md
│       └── shared/
│           ├── alert-thresholds.md      # Enhanced with oncology
│           ├── devices.md
│           ├── comorbidity-matrix.md    # Enhanced with cancer+comorbidities
│           ├── nurse-response-protocols.md # Enhanced with oncology
│           └── questionnaires/
│               ├── chf-questionnaire.md
│               ├── ...
│               └── oncology-questionnaire.md # ⭐ NEW
```

---

## 🎯 Coverage Summary

### Oncology Pathways (v2.0)

| Category | Pathways | Focus |
|----------|----------|-------|
| **Critical Symptoms** | Febrile Neutropenia, Pain, Dyspnea | Medical emergencies, immediate intervention |
| **GI Symptoms** | Nausea/Vomiting, Diarrhea, Constipation, Mucositis | Nutritional support, hydration |
| **Neuro/Psych** | Fatigue, Neuropathy (CIPN), Distress, Sleep | Quality of life, safety |
| **Physical** | Lymphedema, Skin Rash | Long-term management |
| **Treatment** | RET+ Lung Cancer | Targeted therapy protocols |

### Disease Pathways (v1.0)

| Care Level | Diseases | Duration |
|------------|----------|----------|
| **Acute** | CHF, COPD, Pneumonia, HTN, Diabetes, DVT, COVID | 2-10 days |
| **Post-Acute** | Same 7 diseases | 14-90 days |

---

## 📚 Documentation

- **[RELEASE.md](RELEASE.md)** - Detailed v2.0 release notes
- **[SKILL.md](.opencode/skills/carepath-oncology/SKILL.md)** - Oncology skill documentation
- **[QA Scenarios](.opencode/skills/carepath-oncology/assets/qa-scenarios-oncology.md)** - Test cases

---

## 🔗 Related Resources

**Clinical Guidelines**:
- NCCN Guidelines for Supportive Care (Oncology)
- ESMO Clinical Practice Guidelines
- ASCO Clinical Practice Guidelines
- ACC/AHA Heart Failure Guidelines
- GOLD COPD Guidelines
- IDSA/ATS Pneumonia Guidelines
- ADA Standards of Diabetes Care

**Technology**:
- [OpenCode Documentation](https://opencode.dev/docs)
- [Qwen-Pro API](https://qwen.ai/)

---

## 📄 License

Apache License 2.0 - See [LICENSE](LICENSE) for details.

**Clinical Disclaimer**: These skills provide clinical decision support. Not a substitute for professional medical judgment.

---

*Made with ❤️ for healthcare AI*

*Improving patient outcomes through structured clinical decision support.*
