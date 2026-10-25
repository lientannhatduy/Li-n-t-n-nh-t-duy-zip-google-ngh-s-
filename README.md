# Li-n-t-n-nh-t-duy-zip-google-ngh-s-
#!/usr/bin/env bash
set -euo pipefail

REPO_DIR="wikidata-lien-tan-nhat-duy"

mkdir -p "$REPO_DIR/data" \
         "$REPO_DIR/quickstatements" \
         "$REPO_DIR/.github/workflows" \
         "$REPO_DIR/.github/ISSUE_TEMPLATE"

cat > "$REPO_DIR/README.md" <<'EOF'
# Wikidata data for Liên Tấn Nhật Duy

This repository contains structured metadata and import statements for Liên Tấn Nhật Duy, also known publicly as DJ D.R TheBattery.

## Repository contents

- `data/lien-tan-nhat-duy.jsonld` — JSON-LD metadata for a Person
- `quickstatements/lien-tan-nhat-duy.txt` — QuickStatements payload for import into Wikidata
- `LICENSE` — repository license
- `CODE_OF_CONDUCT.md` — community guidelines
- `SECURITY.md` — vulnerability disclosure guidance
- `.gitignore` — local exclusions
- `.github/ISSUE_TEMPLATE/` — issue templates
- `.github/pull_request_template.md` — PR template
- `.github/workflows/validate.yml` — automated validation

## Purpose

This repository is intended to support the creation or refinement of a Wikidata item for a Vietnamese DJ and music producer using the public alias DJ D.R TheBattery.

The metadata currently includes:
- name
- alternate name
- birth date
- occupation
- nationality
- public profile links
- identifiers associated with public accounts

## QuickStatements

To import the data into Wikidata:

1. Open https://quickstatements.toolforge.org/
2. Sign in with your Wikidata account
3. Copy the contents of `quickstatements/lien-tan-nhat-duy.txt`
4. Paste them into the input box
5. Click "Check" and then "Run"

## Validation

The repository includes a simple GitHub Actions workflow to validate that:
- `data/lien-tan-nhat-duy.jsonld` is valid JSON
- the required metadata files exist

## Contributing

Contributions are welcome. Please keep the dataset conservative, factual, and aligned with the public record. Avoid speculative claims or unsupported assertions.

## Security

Please review `SECURITY.md` for guidance on responsible disclosure of security concerns.

## License

This repository is licensed under CC0 1.0 Universal.
EOF

cat > "$REPO_DIR/LICENSE" <<'EOF'
Creative Commons Zero v1.0 Universal

This work is dedicated to the public domain under the Creative Commons CC0 1.0 Universal Public Domain Dedication.

You can copy, modify, distribute, and perform the work, even for commercial purposes, all without asking permission.

No warranty is offered. The work is provided "as is".

For the full legal text, see:
https://creativecommons.org/publicdomain/zero/1.0/
EOF

cat > "$REPO_DIR/CODE_OF_CONDUCT.md" <<'EOF'
# Contributor Covenant Code of Conduct

## Our Pledge

We as members, contributors, and leaders pledge to make participation in this project a harassment-free experience for everyone, regardless of age, body size, visible or invisible disability, ethnicity, sex characteristics, gender identity and expression, level of experience, education, socio-economic status, nationality, religion, or sexual orientation.

We pledge to act and interact in ways that contribute to a respectful, inclusive, and productive community.

## Our Standards

Examples of behavior that contributes to a positive environment include:

- demonstrating empathy and kindness toward other people
- being respectful of differing opinions, viewpoints, and experiences
- giving and gracefully accepting constructive feedback
- accepting responsibility and apologizing to those affected by our mistakes
- focusing on what is best not just for us as individuals, but for the overall community

Examples of unacceptable behavior include:

- the use of sexualized language or imagery
- trolling, insulting, or derogatory comments
- public or private harassment
- publishing others' private information without explicit permission
- other conduct that could reasonably be considered inappropriate in a professional setting

## Enforcement Responsibilities

Project maintainers are responsible for clarifying and enforcing our standards of acceptable behavior and will take appropriate and fair corrective action in response to any behavior that they deem inappropriate, threatening, offensive, or harmful.

## Scope

This Code of Conduct applies within all project spaces and in public spaces when an individual is representing the project or its community.

## Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported to the project maintainers through GitHub issues or by contacting the maintainers directly through the repository's contact methods.

All complaints will be reviewed and investigated promptly and fairly.

## Attribution

This Code of Conduct is adapted from the Contributor Covenant, version 2.1, available at https://www.contributor-covenant.org/version/2/1/code_of_conduct.html.

For answers to common questions about this code of conduct, see the FAQ at https://www.contributor-covenant.org/faq.
EOF

cat > "$REPO_DIR/SECURITY.md" <<'EOF'
# Security Policy

## Supported Versions

This project is maintained as a lightweight public dataset repository. Security issues are handled on a best-effort basis.

## Reporting a Vulnerability

If you discover a security issue, please report it privately through GitHub Security Advisories.

Do not open a public issue for security vulnerabilities. Please provide as much detail as possible so the maintainers can review and address the issue quickly.

## Response Expectations

We aim to acknowledge receipt of the report as quickly as possible and to provide a clear path toward remediation.

## Disclosure Policy

We ask that reporters keep vulnerabilities confidential until a fix has been released or the issue has been assessed and approved for public disclosure.
EOF

cat > "$REPO_DIR/.gitignore" <<'EOF'
# OS
.DS_Store
Thumbs.db

# Editors
.vscode/
.idea/
*.swp
*.swo

# Temporary files
*.tmp
*.log

# Environment
.env
.env.*
EOF

cat > "$REPO_DIR/.github/ISSUE_TEMPLATE/config.yml" <<'EOF'
blank_issues_enabled: true
EOF

cat > "$REPO_DIR/.github/ISSUE_TEMPLATE/bug_report.md" <<'EOF'
---
name: Bug report
about: Report an issue or problem in the dataset or repository
title: ""
labels: bug
assignees: ""
---

## Summary

A clear and concise description of the bug.

## Problem

Describe what is wrong or what is not working as expected.

## Steps to reproduce

1. Go to '...'
2. Open '...'
3. Observe '...'

## Expected behavior

Describe what you expected to happen.

## Actual behavior

Describe what actually happened.

## Metadata impact

If relevant, specify which file or data entry is affected, for example:
- `data/lien-tan-nhat-duy.jsonld`
- `quickstatements/lien-tan-nhat-duy.txt`

## Environment

- OS: [e.g. Ubuntu, macOS, Windows]
- Browser: [if applicable]
- GitHub UI / local environment: [if applicable]

## Additional context

Add any other context, links, screenshots, or notes here.
EOF

cat > "$REPO_DIR/.github/ISSUE_TEMPLATE/feature_request.md" <<'EOF'
---
name: Feature request
about: Suggest an improvement or enhancement
title: ""
labels: enhancement
assignees: ""
---

## Summary

A clear and concise description of the feature or improvement.

## Problem to solve

Explain the problem or use case that motivated this request.

## Proposed solution

Describe the proposed solution or enhancement.

## Alternatives considered

List any alternative approaches you considered.

## Impact

Describe who would benefit and how this change could improve the dataset or project workflow.

## Additional context

Add any relevant links, examples, screenshots, or supporting references here.
EOF

cat > "$REPO_DIR/.github/pull_request_template.md" <<'EOF'
## Summary

Describe the change and the motivation behind it.

## Scope

- [ ] Data update
- [ ] Documentation update
- [ ] Workflow or automation change
- [ ] Metadata improvement
- [ ] Other: _________

## Changes made

- [ ] Updated dataset metadata
- [ ] Updated documentation
- [ ] Updated QuickStatements payload
- [ ] Adjusted workflows or automation
- [ ] Added or updated tests/checks

## Validation

Describe how the change was validated.

Examples:
- JSON validation passed
- QuickStatements syntax reviewed
- Manual review of output
- GitHub Actions workflow ran successfully

## Notes

Add any additional context, caveats, or follow-up items here.
EOF

cat > "$REPO_DIR/.github/workflows/validate.yml" <<'EOF'
name: Validate metadata

on:
  push:
    branches: ["**"]
  pull_request:

jobs:
  validate:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.12"

      - name: Validate JSON and required files
        run: |
          python - <<'PY'
          import json
          from pathlib import Path

          root = Path(".")
          json_path = root / "data" / "lien-tan-nhat-duy.jsonld"
          quick_path = root / "quickstatements" / "lien-tan-nhat-duy.txt"

          if not json_path.exists():
              raise FileNotFoundError(f"Missing file: {json_path}")
          if not quick_path.exists():
              raise FileNotFoundError(f"Missing file: {quick_path}")

          with json_path.open("r", encoding="utf-8") as f:
              json.load(f)

          print("Metadata validation passed.")
          PY
EOF

cat > "$REPO_DIR/data/lien-tan-nhat-duy.jsonld" <<'EOF'
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Liên Tấn Nhật Duy",
  "alternateName": "DJ D.R TheBattery",
  "birthDate": "2002-11-16",
  "jobTitle": [
    "DJ",
    "Music Producer"
  ],
  "description": "Liên Tấn Nhật Duy is a Vietnamese DJ and music producer, born on 16 November 2002. He is publicly known under the alias DJ D.R TheBattery and maintains public profiles across social media platforms.",
  "image": "IMG_20260405_191258.jpg",
  "nationality": "Vietnam",
  "identifier": {
    "@type": "PropertyValue",
    "propertyID": "Wikidata",
    "value": "Q139987052"
  },
  "sameAs": [
    "https://youtube.com/@lientannhatduy",
    "https://www.facebook.com/share/18axhnhFtg/",
    "https://x.com/lientannhatduy",
    "https://www.instagram.com/lientannhatduysinger",
    "https://www.tiktok.com/@lientannhatduy",
    "https://github.com/lientannhatduy",
    "https://www.wikidata.org/wiki/Q139987052"
  ],
  "mainEntityOfPage": "https://youtube.com/@lientannhatduy"
}
EOF

cat > "$REPO_DIR/quickstatements/lien-tan-nhat-duy.txt" <<'EOF'
CREATE
LAST|L@vi|Liên Tấn Nhật Duy
LAST|D@vi|DJ và nhà sản xuất âm nhạc người Việt Nam, sinh ngày 16 tháng 11 năm 2002, hoạt động dưới nghệ danh DJ D.R TheBattery.
LAST|ALIASES@vi|"DJ D.R TheBattery"
LAST|P31|Q5
LAST|P569|+2002-11-16T00:00:00Z/11|S854|"https://youtube.com/@lientannhatduy"
LAST|P106|Q181930|S854|"https://youtube.com/@lientannhatduy"
LAST|P106|Q2526255|S854|"https://youtube.com/@lientannhatduy"
LAST|P27|Q881|S854|"https://youtube.com/@lientannhatduy"
LAST|P18|"File:IMG_20260405_191258.jpg"
LAST|P856|"https://youtube.com/@lientannhatduy"
LAST|P2002|"lientannhatduy"
LAST|P2003|"lientannhatduysinger"
LAST|P7085|"lientannhatduy"
EOF

zip -r "${REPO_DIR}.zip" "$REPO_DIR" >/dev/null
echo "Created zip: ${REPO_DIR}.zip"

ls -lh "${REPO_DIR}.zip"
