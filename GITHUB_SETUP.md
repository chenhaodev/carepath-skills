# GitHub Repository Setup Instructions

**Purpose**: Step-by-step guide to publish your Carepath OpenCode Skills repository to GitHub.

---

## Prerequisites

- ✅ Git repository initialized locally (already done - commit `f048b8e`)
- ✅ All skill files committed
- ✅ GitHub account created
- ✅ Git configured with your credentials

---

## Step 1: Create GitHub Repository

### Option A: Via GitHub Web Interface (Recommended)

1. **Go to GitHub**: [https://github.com/new](https://github.com/new)

2. **Repository Settings**:
   - **Repository name**: `carepath-skills` (or your preferred name)
   - **Description**: `Clinical decision support OpenCode skills for remote patient monitoring across 7 disease pathways (CHF, COPD, Pneumonia, HTN, Diabetes, DVT, COVID-19)`
   - **Visibility**: ✅ **Public** (required for OpenCode skill sharing)
   - **Initialize repository**: ❌ **DO NOT check** any boxes
     - NO README (you already have one)
     - NO .gitignore (you already have one)
     - NO license (you already have Apache 2.0)

3. **Click "Create repository"**

### Option B: Via GitHub CLI

```bash
# If you have GitHub CLI installed
gh repo create carepath-skills \
  --public \
  --description "Clinical decision support OpenCode skills for remote patient monitoring" \
  --source=. \
  --remote=origin \
  --push
```

If using GitHub CLI, **skip to Step 4** (it handles push automatically).

---

## Step 2: Add GitHub Remote

**After creating the empty repository on GitHub**, you'll see instructions. Follow "push an existing repository" section:

```bash
# In /Users/chenhao/OpenCode/carepath-skills

# Add GitHub remote (replace YOUR-USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR-USERNAME/carepath-skills.git

# Verify remote was added
git remote -v
```

**Expected output**:
```
origin  https://github.com/YOUR-USERNAME/carepath-skills.git (fetch)
origin  https://github.com/YOUR-USERNAME/carepath-skills.git (push)
```

---

## Step 3: Push to GitHub

```bash
# Push to GitHub (first time)
git push -u origin main

# If your default branch is 'master' instead of 'main', use:
# git push -u origin master
```

**Authentication**:
- GitHub will prompt for username and password
- **Important**: Use a **Personal Access Token** instead of password
  - Create token: GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
  - Required scopes: `repo` (full control of private repositories)
  - Save token securely - you won't see it again

**Expected output**:
```
Enumerating objects: 38, done.
Counting objects: 100% (38/38), done.
Delta compression using up to 8 threads
Compressing objects: 100% (35/35), done.
Writing objects: 100% (38/38), [size], done.
Total 38 (delta 2), reused 0 (delta 0)
To https://github.com/YOUR-USERNAME/carepath-skills.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

---

## Step 4: Configure Repository Settings

### Repository Topics (Tags)

Add topics to help users discover your repository:

1. Go to your repository on GitHub
2. Click "About" ⚙️ (gear icon on right side)
3. Add topics:
   - `opencode`
   - `opencode-skills`
   - `remote-patient-monitoring`
   - `clinical-decision-support`
   - `chf`
   - `copd`
   - `qwen-pro`
   - `healthcare`
   - `telemedicine`
4. Save changes

### Repository Description

Ensure the description is set (should be from Step 1):

> Clinical decision support OpenCode skills for remote patient monitoring across 7 disease pathways (CHF, COPD, Pneumonia, HTN, Diabetes, DVT, COVID-19)

### Website (Optional)

If you have documentation hosted elsewhere, add the URL in "Website" field.

---

## Step 5: Create Release Tag (v1.0.0)

### Via GitHub Web Interface

1. Go to your repository
2. Click "Releases" (right sidebar or `/releases` path)
3. Click "Create a new release"
4. **Tag version**: `v1.0.0`
5. **Release title**: `v1.0.0 - Initial Release`
6. **Description**: Copy from CHANGELOG.md (v1.0.0 section)
7. **Attach binaries**: None needed (skills are markdown files)
8. ✅ Check "Set as the latest release"
9. Click "Publish release"

### Via Git Command Line

```bash
# Create annotated tag locally
git tag -a v1.0.0 -m "Release v1.0.0 - Initial carepath skills"

# Push tag to GitHub
git push origin v1.0.0

# Then create release on GitHub web interface using this tag
```

---

## Step 6: Update README.md with GitHub URLs

**Edit README.md** to replace placeholder URLs:

```bash
# Open README.md in editor
# Find and replace:
# - YOUR-USERNAME → your actual GitHub username
# - https://github.com/YOUR-USERNAME/carepath-skills → actual repository URL

# Example replacements:
# Before: https://github.com/YOUR-USERNAME/carepath-skills/issues
# After:  https://github.com/johndoe/carepath-skills/issues
```

**Commit and push the update**:

```bash
git add README.md
git commit -m "docs: update README with actual GitHub repository URLs"
git push origin main
```

---

## Step 7: Enable GitHub Features

### Issues

Issues are enabled by default. Configure labels:

1. Go to repository → Issues → Labels
2. Recommended labels (add these):
   - `bug` (clinical content error)
   - `enhancement` (new disease pathway)
   - `documentation`
   - `clinical-review-needed`
   - `good-first-issue`

### Discussions (Optional)

Enable for community Q&A:

1. Settings → Features → Discussions → Check "Discussions"
2. Set up categories:
   - General
   - Clinical Questions
   - Feature Requests
   - Show and Tell

### GitHub Pages (Optional)

Host documentation:

1. Settings → Pages
2. Source: Deploy from a branch → `main` → `/docs` or root
3. Save
4. Access at: `https://YOUR-USERNAME.github.io/carepath-skills/`

---

## Step 8: Add Repository to OpenCode Skill Registry (Optional)

If OpenCode maintains a skill registry:

1. Submit pull request to OpenCode skills repository
2. Add your skill metadata:
   ```yaml
   - name: carepath-acute
     repository: https://github.com/YOUR-USERNAME/carepath-skills
     path: .opencode/skills/carepath-acute
     description: Hospital-at-home acute care for 7 diseases
     author: YOUR-NAME
     license: Apache-2.0
   
   - name: carepath-postacute
     repository: https://github.com/YOUR-USERNAME/carepath-skills
     path: .opencode/skills/carepath-postacute
     description: Post-discharge readmission prevention for 7 diseases
     author: YOUR-NAME
     license: Apache-2.0
   ```

---

## Step 9: Share with Community

### Announce on Social Media/Forums

- **Twitter/X**: Share repository with `#OpenCode #RemotePatientMonitoring #Healthcare`
- **LinkedIn**: Post about the release, tag relevant healthcare tech groups
- **Reddit**: r/HealthIT, r/medicine (if appropriate)
- **OpenCode Community**: Discord, Slack, or forum

### Sample Announcement

```
🚀 Just released Carepath OpenCode Skills v1.0.0!

Clinical decision support for remote patient monitoring across 7 diseases:
✅ CHF, COPD, Pneumonia, HTN, Diabetes, DVT, COVID-19
✅ Acute care (hospital-at-home) + Post-acute (readmission prevention)
✅ Evidence-based protocols from ACC/AHA, GOLD, IDSA/ATS, ADA, ACCP, NIH
✅ Optimized for Qwen-Pro API
✅ Apache 2.0 licensed - free to use commercially

🔗 https://github.com/YOUR-USERNAME/carepath-skills

Perfect for telehealth platforms, hospital-at-home programs, and RPM services!
```

---

## Step 10: Set Up Continuous Integration (Optional)

### Validate Cross-References on Every Commit

Create `.github/workflows/validate.yml`:

```yaml
name: Validate Skills

on: [push, pull_request]

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Check for broken internal links
        run: |
          find .opencode/skills -name "*.md" | while read file; do
            echo "Checking $file"
            grep -oP '\[.*?\]\(\K[^)]+' "$file" | while read link; do
              if [[ $link == ../* ]] || [[ $link == ./* ]]; then
                dir=$(dirname "$file")
                target="$dir/$link"
                if [ ! -f "$target" ]; then
                  echo "❌ Broken link in $file: $link"
                  exit 1
                fi
              fi
            done
          done
          echo "✅ All internal links valid"
      
      - name: Validate YAML frontmatter
        run: |
          # Check SKILL.md files have valid frontmatter
          for skill in .opencode/skills/carepath-*/SKILL.md; do
            if ! head -20 "$skill" | grep -q "^name:"; then
              echo "❌ Missing frontmatter in $skill"
              exit 1
            fi
          done
          echo "✅ All SKILL.md files have valid frontmatter"
```

---

## Step 11: Monitor and Maintain

### Watch for Issues

- Set up email notifications for new issues
- Respond within 48 hours (best practice)
- Label issues appropriately

### Keep Content Updated

- Review clinical guidelines annually
- Update CHANGELOG.md for all changes
- Increment version numbers per Semantic Versioning:
  - **Patch** (1.0.1): Bug fixes, typos
  - **Minor** (1.1.0): New features, new disease pathways
  - **Major** (2.0.0): Breaking changes, major restructuring

### Contributors

- Thank contributors in CHANGELOG.md
- Consider adding CONTRIBUTORS.md file

---

## Troubleshooting

### Problem: Push Rejected (Authentication Failed)

**Solution**: Use Personal Access Token instead of password
1. GitHub Settings → Developer settings → Personal access tokens → Generate new token
2. Scopes: `repo`
3. Use token as password when pushing

### Problem: Remote Already Exists

```
error: remote origin already exists
```

**Solution**:
```bash
# Remove existing remote
git remote remove origin

# Add correct remote
git remote add origin https://github.com/YOUR-USERNAME/carepath-skills.git
```

### Problem: Branch Name Mismatch

GitHub uses `main`, your local uses `master`:

**Solution**:
```bash
# Rename local branch to main
git branch -M main

# Then push
git push -u origin main
```

---

## Success Checklist

After completing all steps:

- [ ] Repository created on GitHub (public)
- [ ] All commits pushed to `main` branch
- [ ] v1.0.0 release created
- [ ] Topics/tags added for discoverability
- [ ] README.md updated with actual repository URLs
- [ ] CONTRIBUTING.md accessible
- [ ] LICENSE file visible
- [ ] Repository shared with community
- [ ] Issues/Discussions enabled (optional)
- [ ] GitHub Actions CI set up (optional)

---

## Next Steps

**After GitHub setup**:

1. **User Adoption**:
   - Share installation instructions with early adopters
   - Collect feedback on usability
   - Monitor issues for bug reports

2. **Clinical Validation**:
   - Have SMEs review clinical content
   - Test with real (de-identified) scenarios
   - Document any guideline updates needed

3. **Feature Development** (v1.1.0+):
   - Add QA automation
   - Additional disease pathways (stroke, ACS, sepsis)
   - Translations (Spanish, Mandarin)
   - EMR integration examples

4. **Community Building**:
   - Engage with users in Discussions
   - Accept pull requests
   - Recognize contributors

---

## Support

If you encounter issues during GitHub setup:

- **GitHub Docs**: https://docs.github.com/
- **Git Documentation**: https://git-scm.com/doc
- **OpenCode Community**: [Discord/Slack/Forum]

---

**Congratulations!** 🎉 Your Carepath OpenCode Skills are now publicly available on GitHub for the remote patient monitoring community to use!
