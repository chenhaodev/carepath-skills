# Changelog

All notable changes to the Carepath OpenCode Skills project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-02-01

### Added

#### Core Skills
- **carepath-acute** skill for hospital-at-home acute care monitoring
- **carepath-postacute** skill for post-discharge readmission prevention

#### Disease Coverage (7 Pathways)
- **CHF** (Congestive Heart Failure)
  - Acute: 2-10 days IV diuresis protocol
  - Post-acute: 30-day readmission prevention with KCCQ-12 scoring
- **COPD** (Chronic Obstructive Pulmonary Disease)
  - Acute: 3-7 days exacerbation management
  - Post-acute: 90-day recovery with CAT scoring
- **Pneumonia** (Community-Acquired Pneumonia)
  - Acute: 5-10 days IV antibiotic protocol
  - Post-acute: 30-day recovery monitoring
- **HTN** (Hypertension/Hypertensive Urgency)
  - Acute: 1-3 days IV antihypertensive management
  - Post-acute: 30-day BP optimization
- **Diabetes** (DKA/HHS)
  - Acute: 2-5 days IV insulin + fluids
  - Post-acute: 30-day glucose stabilization
- **DVT** (Deep Vein Thrombosis)
  - Acute: 3-7 days IV anticoagulation
  - Post-acute: 90-day anticoagulation monitoring
- **COVID-19**
  - Acute: 2-6 days with IV antivirals/oxygen support
  - Post-acute: 14-day recovery and long-COVID screening

#### Shared Resources
- **Universal alert thresholds** with 3-tier escalation (Critical/Urgent/Advisory)
- **Device catalog** with specifications for 10+ monitoring devices
- **Comorbidity matrix** covering 25+ disease combinations
- **Nurse-driven response protocols** - Operational workflows for RNs responding to vital alerts (CHF, COPD, HTN)
  - Extracted from Carepath-Logic.pdf via OCR
  - Step-by-step alert response procedures
  - PRN medication instructions
  - Escalation decision trees
- **7 disease-specific questionnaires** with scoring algorithms:
  - CHF: KCCQ-12 (Kansas City Cardiomyopathy Questionnaire)
  - COPD: CAT (COPD Assessment Test)
  - Pneumonia: Daily symptom checker with CURB-65 elements
  - HTN: Hypertensive symptom and emergency screening
  - Diabetes: Hypo/hyperglycemia assessment
  - DVT: PE warning signs and bleeding surveillance
  - COVID-19: Emergency criteria and respiratory/systemic symptoms

#### Transition Protocols
- **Acute → Post-Acute**: Discharge readiness criteria and handoff checklists
- **Post-Acute → Acute**: Escalation criteria for deteriorating patients

#### Documentation
- Comprehensive README.md with installation and usage instructions
- Apache 2.0 LICENSE
- CONTRIBUTING.md with clinical review requirements
- .gitignore configured for OpenCode projects

#### Features
- **Qwen-Pro optimized**: Structured tables, step-by-step protocols, explicit formatting
- **Evidence-based**: References ACC/AHA, GOLD, IDSA/ATS, ADA, ACCP, NIH, CDC guidelines
- **Cross-referenced**: Internal links between related protocols and comorbidities
- **OpenCode compatible**: YAML frontmatter, contextual auto-load triggers

### Clinical Guidelines Referenced
- ACC/AHA Heart Failure Guidelines 2022
- GOLD COPD Guidelines 2023
- IDSA/ATS Pneumonia Guidelines 2019
- AHA/ACC Hypertension Guidelines 2017
- ADA Standards of Diabetes Care 2024
- ACCP Antithrombotic Therapy Guidelines 2021
- NIH COVID-19 Treatment Guidelines 2023

### File Statistics
- Total markdown files: 34 (28 from Carepath-Prod.pdf + 1 from Carepath-Logic.pdf + 3 QA files + 2 documentation files)
- Total lines of clinical content: ~12,000+
- Disease protocols: 14 (7 acute + 7 post-acute)
- Questionnaires: 7
- Shared reference files: 8 (alert-thresholds, devices, comorbidity-matrix, nurse-response-protocols + 4 others)
- QA scenarios: 20 (10 acute + 10 post-acute)
- Example conversations: 5

### Quality Metrics
- 30-day readmission targets: <20% (vs national ~25% for CHF)
- Alert response times: Critical <5min (acute), <1hr (post-acute)
- Patient satisfaction target: >85%
- Medication adherence target: >80%

---

## [Unreleased]

### Planned for Future Releases

#### v1.1.0
- QA scenarios for skill verification
- Example conversation pairs
- Cross-reference validation tooling
- Carepath-Logic.pdf content integration (if OCR yields useful data)

#### v1.2.0
- Additional disease pathways: Stroke, ACS (Acute Coronary Syndrome), Sepsis
- Pediatric adaptations for existing pathways
- Spanish language translations

#### v2.0.0
- Integration with common EMR systems
- API endpoints for threshold lookups
- Automated alert generation examples

---

## Release Notes Template

### [X.Y.Z] - YYYY-MM-DD

#### Added
- New features or disease pathways

#### Changed
- Modifications to existing protocols
- Updated clinical guidelines

#### Deprecated
- Features being phased out

#### Removed
- Discontinued features

#### Fixed
- Bug fixes and clinical content corrections

#### Security
- Security-related changes

---

[1.0.0]: https://github.com/YOUR-USERNAME/carepath-skills/releases/tag/v1.0.0
