# Carepath Skills v2.0 Release Notes

**Release Date**: 2026-02-05  
**Version**: 2.0.0

---

## 🎉 Announcement

We're excited to announce **Carepath Skills v2.0** - a major release adding comprehensive oncology support including 18 symptom management pathways and the first cancer-type specific treatment pathway (RET+ Lung Cancer).

---

## ✨ What's New

### 🆕 carepath-oncology Skill

A new OpenCode skill dedicated to oncology clinical decision support:

| Component | Count | Description |
|-----------|-------|-------------|
| **Symptom Pathways** | 18 | Comprehensive symptom management (Fever, Pain, Nausea, etc.) |
| **Treatment Pathways** | 1 | Cancer-type specific protocols (RET+ Lung Cancer) |
| **Questionnaires** | 1 | Daily symptom surveillance (ESAS-r based) |
| **QA Scenarios** | 4 | Realistic test cases (Emergency, Urgent, Chronic, Psych) |

### 🆕 RET Fusion-Positive Lung Cancer Pathway

First cancer-type specific treatment pathway covering:

- **First-Line Targeted Therapy**: Selpercatinib (Retevmo) and Pralsetinib (Gavreto)
- **Dosing & Administration**: Complete dose schedules and modifications
- **Monitoring Protocol**: Labs, imaging, response assessment timeline
- **Adverse Event Management**: Hypertension, diarrhea, pneumonitis, QTc prolongation
- **Drug Interactions**: CYP3A4 interactions, PPI effects
- **Resistance Management**: Second-line options

### 🆕 Enhanced Shared Resources

| Resource | Updates |
|----------|---------|
| **alert-thresholds.md** | Added oncology-specific thresholds (Fever ≥38°C in neutropenia, CTCAE grading) |
| **nurse-response-protocols.md** | Added Febrile Neutropenia Protocol, C-SSRS Suicide Risk Protocol |
| **comorbidity-matrix.md** | Added Cancer + Diabetes, Cancer + CHF, Cancer + COPD, Cancer + CKD, Cancer + Depression |
| **questionnaires/** | Added oncology-questionnaire.md (Distress Thermometer, Pain, GI symptoms, Psych screening) |

---

## 📊 Statistics

### Files Changed

| Category | Files | Lines Added |
|----------|-------|-------------|
| **New Skill** | 1 | ~260 |
| **Symptom Pathways** | 12 | ~1,700 |
| **Treatment Pathways** | 1 | ~360 |
| **Questionnaire** | 1 | ~200 |
| **QA Scenarios** | 1 | ~220 |
| **Shared Resources** | 3 | ~400 |
| **README Updates** | 1 | ~100 |
| **Release Notes** | 1 | ~100 |
| **Total** | **20+** | **~3,000+** |

### Skill Coverage

| Skill | Pathways | Status |
|-------|----------|--------|
| **carepath-acute** | 7 disease pathways | ✅ v1.0 |
| **carepath-postacute** | 7 disease pathways | ✅ v1.0 |
| **carepath-oncology** | 18 symptoms + 1 treatment | 🆕 v2.0 |

---

## 🚀 Installation

### New Installation (v2.0)

```bash
# Clone repository
git clone https://github.com/chenhaodev/carepath-skills.git
cd carepath-skills

# Copy all skills
cp -r .opencode/skills/* ~/.opencode/skills/

# Verify
opencode list-skills
```

Expected output:
```
carepath-acute
carepath-postacute
carepath-oncology
shared
```

### Upgrade from v1.0

```bash
# Navigate to repository
cd carepath-skills
git pull origin main

# Copy new oncology skill
cp -r .opencode/skills/carepath-oncology ~/.opencode/skills/
cp -r .opencode/skills/shared/* ~/.opencode/skills/shared/

# Verify
opencode list-skills
```

---

## 📖 Usage Examples

### Oncology: Febrile Neutropenia

```
User: "Patient on chemo reports fever of 38.5°C. What do I do?"

OpenCode Response:
→ Identifies: Febrile Neutropenia (MEDICAL EMERGY)
→ References: symptom-febrile-neutropenia.md
→ Action: IMMEDIATE ED referral + Notify oncologist
→ Golden Hour: Antibiotics within 60 minutes
```

### Oncology: RET+ Lung Cancer Treatment

```
User: "Newly diagnosed RET+ lung cancer. What's first-line treatment?"

OpenCode Response:
→ References: treatment-ret-positive-lung-cancer.md
→ First-line: Selpercatinib 160mg BID OR Pralsetinib 400mg QD
→ Baseline: CBC, CMP, TSH, ECG, BP, Brain MRI
→ Monitoring: Week 2, 4, 8, then q8-12 weeks
→ AEs: Hypertension, diarrhea, dry mouth management
```

### Acute Care: CHF Exacerbation

```
User: "CHF patient needs IV diuresis at home."

OpenCode Response:
→ References: chf-acute.md
→ Protocol: IV furosemide 40-80mg daily
→ Monitoring: Daily weights, BP, symptoms
→ Alert: Weight gain ≥3 lbs/3 days = urgent diuretic adjustment
```

---

## 🔧 Configuration

### OpenCode config.yml

```yaml
skills:
  carepath-acute:
    enabled: true
    auto_load: true

  carepath-postacute:
    enabled: true
    auto_load: true

  carepath-oncology:       # ⭐ NEW in v2.0
    enabled: true
    auto_load: true

models:
  default: qwen-pro
```

---

## 📋 Changelog

### v2.0.0 (2026-02-05)

#### New Features
- 🆕 Added carepath-oncology skill with 18 symptom pathways
- 🆕 Added RET+ Lung Cancer treatment pathway
- 🆕 Added oncology questionnaire (Distress Thermometer + symptom screening)
- 🆕 Added 4 QA scenarios for oncology testing
- 🆕 Enhanced shared resources with oncology content

#### Oncology Symptom Pathways Added
1. symptom-febrile-neutropenia.md (Critical)
2. symptom-pain.md (Critical)
3. symptom-dyspnea.md (Critical)
4. symptom-nausea-vomiting.md (Urgent)
5. symptom-diarrhea.md (Urgent)
6. symptom-constipation.md (Advisory)
7. symptom-mucositis.md (Urgent)
8. symptom-fatigue.md (Advisory)
9. symptom-neuropathy.md (Advisory)
10. symptom-distress.md (Urgent)
11. symptom-sleep.md (Advisory)
12. symptom-lymphedema.md (Advisory)

#### Shared Resource Updates
- alert-thresholds.md: Added oncology-specific thresholds
- nurse-response-protocols.md: Added oncology protocols
- comorbidity-matrix.md: Added cancer + comorbidity combinations
- questionnaires/oncology-questionnaire.md: Added

#### Documentation
- Updated README.md
- Created RELEASE.md (this file)
- Updated SKILL.md with new treatment pathway reference

---

## 🙏 Acknowledgments

**Clinical Content Sources**:
- Singapore Cancer Network Clinical Pathway Guide
- NCCN Guidelines for Supportive Care (v3.2025)
- ESMO Clinical Practice Guidelines (2024)
- ASCO Clinical Practice Guidelines
- LIBRETTO-001/431 Trials (Selpercatinib)
- ARROW Trial (Pralsetinib)
- CTCAE v5.0 (Common Terminology Criteria for Adverse Events)

**Contributors**:
- Initial oncology pathways developed using AI-assisted documentation

---

## 📞 Support

**Issues**: [GitHub Issues](https://github.com/chenhaodev/carepath-skills/issues)

**Email**: chenhaomails@gmail.com

---

## 🔜 Future Roadmap

### Planned for v2.1
- [ ] EGFR-mutant Lung Cancer pathway
- [ ] ALK-positive Lung Cancer pathway
- [ ] Breast Cancer pathways (HER2+, HR+)
- [ ] Colorectal Cancer pathways
- [ ] Immunotherapy-specific toxicity pathways

### Planned for v3.0
- [ ] Pediatric oncology adaptations
- [ ] Palliative care pathways
- [ ] Integration with EMR systems
- [ ] Multi-language support

---

**Made with ❤️ for healthcare AI**

*Improving patient outcomes through structured clinical decision support.*
