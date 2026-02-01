# Contributing to Carepath OpenCode Skills

Thank you for your interest in contributing to Carepath OpenCode Skills! This project provides clinical decision support for remote patient monitoring across 7 disease pathways.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Reporting Issues](#reporting-issues)
- [Suggesting Enhancements](#suggesting-enhancements)
- [Contributing Clinical Content](#contributing-clinical-content)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Clinical Review Requirements](#clinical-review-requirements)

---

## Code of Conduct

This project adheres to a professional code of conduct. By participating, you are expected to uphold this standard:

- **Be respectful**: Treat all contributors with respect and kindness
- **Be constructive**: Provide helpful feedback and suggestions
- **Be collaborative**: Work together to improve the project
- **Prioritize patient safety**: Clinical accuracy takes precedence over all other concerns

---

## How Can I Contribute?

### Reporting Issues

**Before submitting an issue**, please:

1. **Search existing issues** to avoid duplicates
2. **Check the documentation** (README.md and skill reference files)
3. **Verify the issue** with the latest version

**When creating an issue**, include:

- **Clear title**: Summarize the issue in one line
- **Description**: Detailed explanation of the problem
- **Steps to reproduce**: How to recreate the issue
- **Expected behavior**: What should happen
- **Actual behavior**: What actually happens
- **Skill/pathway affected**: Which disease or skill (acute/post-acute)
- **Clinical context**: Patient scenario if relevant (use synthetic data only - no PHI)

**Issue Types:**

- 🐛 **Bug Report**: Clinical content errors, broken links, incorrect thresholds
- 📖 **Documentation**: Unclear instructions, missing information
- 🏥 **Clinical Accuracy**: Outdated guidelines, incorrect clinical information
- ✨ **Feature Request**: New disease pathways, additional questionnaires

---

## Suggesting Enhancements

We welcome suggestions for:

- **New disease pathways** (e.g., stroke, ACS, sepsis, CKD)
- **Additional questionnaires or assessments**
- **Enhanced alert threshold logic**
- **Improved comorbidity guidance**
- **Translation to other languages**

**Enhancement proposals should include:**

1. **Clinical rationale**: Why is this enhancement valuable?
2. **Evidence base**: Guidelines or studies supporting the enhancement
3. **Implementation scope**: What files/sections would be affected?
4. **Backward compatibility**: Impact on existing workflows

---

## Contributing Clinical Content

### Clinical Content Guidelines

**ALL clinical content changes MUST**:

1. **Be evidence-based**: Reference current clinical guidelines (ACC/AHA, GOLD, IDSA/ATS, ADA, ACCP, NIH, CDC)
2. **Include source citations**: Link to guideline year and organization
3. **Avoid medication dosing**: This project provides thresholds and protocols, not prescriptive dosing
4. **Use synthetic data**: NEVER include real patient information (PHI)
5. **Follow Qwen-Pro optimization**: Structured tables, step-by-step instructions, explicit formatting

### Content Structure Requirements

**For new disease pathways**, include:

- **Acute care protocol** (`.opencode/skills/carepath-acute/references/[disease]-acute.md`)
  - Objective and duration
  - Eligibility criteria (inclusion/exclusion)
  - Devices and monitoring equipment
  - Daily monitoring protocol
  - Alert thresholds and escalations
  - Treatment protocol overview (not dosing)
  - Complications to watch for
  - Comorbidity considerations

- **Post-acute care protocol** (`.opencode/skills/carepath-postacute/references/[disease]-postacute.md`)
  - Same structure, focused on readmission prevention

- **Questionnaire** (`.opencode/skills/shared/questionnaires/[disease]-questionnaire.md`)
  - Daily symptom assessment questions
  - Scoring algorithm (if applicable)
  - Clinical interpretation of scores
  - Emergency criteria (when to call 911)

- **Updates to shared resources**:
  - Alert thresholds (`.opencode/skills/shared/alert-thresholds.md`)
  - Device requirements (`.opencode/skills/shared/devices.md`)
  - Comorbidity matrix (`.opencode/skills/shared/comorbidity-matrix.md`)

---

## Pull Request Process

### 1. Fork and Branch

```bash
# Fork the repository on GitHub
# Clone your fork
git clone https://github.com/YOUR-USERNAME/carepath-skills.git
cd carepath-skills

# Create a feature branch
git checkout -b feature/disease-pathway-name
# or
git checkout -b fix/clinical-accuracy-issue
```

### 2. Make Changes

- **Follow existing file structure**
- **Match formatting style** (see Coding Standards below)
- **Update BOTH acute and post-acute** if adding a disease
- **Add cross-references** to related files
- **Test cross-references** to ensure links resolve

### 3. Commit Changes

```bash
# Stage your changes
git add .

# Commit with descriptive message
git commit -m "feat(disease): add stroke acute care pathway with NIHSS scoring"
# or
git commit -m "fix(chf): correct KCCQ-12 scoring interpretation"
```

**Commit message format:**

```
<type>(<scope>): <short description>

[optional body]
[optional footer]
```

**Types:**
- `feat`: New feature (disease pathway, questionnaire)
- `fix`: Bug fix (clinical content correction)
- `docs`: Documentation only
- `refactor`: Code restructuring without functionality change
- `test`: Adding or updating QA scenarios

**Scopes:**
- `acute`, `postacute`, `shared`, `questionnaires`, `disease-name`

### 4. Push and Create PR

```bash
# Push to your fork
git push origin feature/disease-pathway-name

# Go to GitHub and create Pull Request
```

**Pull Request Template:**

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] New disease pathway
- [ ] Clinical content fix
- [ ] Documentation update
- [ ] Questionnaire addition
- [ ] Alert threshold modification

## Clinical Evidence Base
- Guideline: [e.g., AHA/ACC 2024 Stroke Guidelines]
- Reference: [Link to guideline]

## Checklist
- [ ] All files follow existing structure
- [ ] Cross-references updated
- [ ] No PHI in examples
- [ ] Evidence-based content with citations
- [ ] Qwen-Pro optimized formatting (tables, lists)
- [ ] Self-reviewed for clinical accuracy

## Testing
- [ ] Verified all internal links resolve
- [ ] Checked alert thresholds against guidelines
- [ ] Validated questionnaire scoring logic
```

### 5. Code Review Process

**Your PR will be reviewed for:**

1. **Clinical accuracy** (requires subject matter expert approval)
2. **Evidence base** (guidelines cited and current)
3. **Formatting consistency** (matches existing style)
4. **Cross-reference integrity** (all links work)
5. **No PHI** (synthetic data only)

**Reviewers may request:**
- Additional citations
- Formatting changes
- Clinical clarifications
- Evidence for novel recommendations

### 6. Merge

Once approved:
- PR will be merged to `main`
- Contributors will be acknowledged in CHANGELOG.md

---

## Coding Standards

### Markdown Formatting

**Headers:**
```markdown
# Top-level (skill name only)
## Major sections
### Subsections
#### Details
```

**Tables** (preferred for structured data):
```markdown
| Parameter | Threshold | Units | Clinical Significance |
|-----------|-----------|-------|----------------------|
| SpO2 | <92% | % | Hypoxemia |
```

**Lists:**
```markdown
- Use bullet lists for non-sequential items
- Keep items concise (one line preferred)

1. Use numbered lists for step-by-step instructions
2. Each step should be actionable
```

**Links:**
```markdown
<!-- Relative internal links -->
[CHF Questionnaire](../../shared/questionnaires/chf-questionnaire.md)

<!-- External links -->
[ACC/AHA Guidelines](https://www.ahajournals.org/guidelines)
```

**Emphasis:**
- **Bold** for critical warnings, medications, key terms
- *Italics* sparingly for emphasis
- `Code blocks` for parameters, values, commands

### File Naming

```
disease-acute.md          # lowercase, hyphen-separated
disease-postacute.md
disease-questionnaire.md
```

### YAML Frontmatter (SKILL.md files only)

```yaml
---
name: carepath-acute
description: |
  Brief description with clinical triggers.
  **Triggers**: keyword1, keyword2, keyword3
version: "1.0.0"
author: "Carepath Team"
license: "Apache-2.0"
---
```

---

## Clinical Review Requirements

### Mandatory for ALL Clinical Content Changes

**Changes to clinical content REQUIRE review by**:

1. **Subject Matter Expert** (physician, NP, PA with relevant specialty)
   - Cardiologist for CHF
   - Pulmonologist for COPD/Pneumonia
   - Endocrinologist for Diabetes
   - Etc.

2. **Evidence Review**
   - Guidelines cited must be current (within 2-3 years)
   - Significant deviations from guidelines must be documented

3. **Safety Review**
   - Emergency criteria (911 triggers) must be explicit
   - Alert thresholds must err on side of patient safety

### Clinical Content NOT Allowed

**Do NOT include:**
- Medication dosing recommendations
- Drug-drug interaction warnings
- Diagnostic conclusions ("patient has X disease")
- Custom treatment protocols (only guideline-based)
- Real patient data or PHI

### Clinical Disclaimer

All skills include this disclaimer:

> These skills provide clinical decision support based on published guidelines. They are NOT a substitute for professional medical judgment. Always verify recommendations against your local protocols, institutional guidelines, and individual patient circumstances. Users assume all responsibility for clinical decisions.

**This disclaimer must remain in all skill files.**

---

## Questions?

- **GitHub Issues**: [Create an issue](https://github.com/YOUR-USERNAME/carepath-skills/issues)
- **GitHub Discussions**: [Ask a question](https://github.com/YOUR-USERNAME/carepath-skills/discussions)

Thank you for contributing to Carepath OpenCode Skills! 🏥
