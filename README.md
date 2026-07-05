# Vendor Risk Assessment Framework Build

> A structured, documentation-driven framework for assessing and categorising third-party vendor risk, built to NIST CSF standards and designed to slot directly into an enterprise GRC programme.

## Overview

Third-party vendors are one of the most persistent and undermanaged risk surfaces in any organisation. A single misconfigured integration or an undisclosed subprocessor can expose customer data, trigger regulatory penalties, and erode trust overnight. This project builds a complete vendor risk assessment framework from the ground up, covering everything from initial intake through risk scoring, categorisation, and ongoing monitoring documentation.

The framework is designed around the NIST Cybersecurity Framework (CSF) and maps vendor controls to its five core functions: Identify, Protect, Detect, Respond, and Recover. Every artefact in this repo reflects the kind of repeatable, auditable process that a GRC team at scale actually needs, not a one-off checklist.

For a GRC Analyst II role, the ability to own the third-party risk lifecycle independently is table stakes. This project demonstrates that I can design the process, build the documentation, apply consistent risk logic, and produce outputs that are immediately usable by legal, security, and procurement stakeholders.

## What I Built / Key Features

- **Vendor Intake Questionnaire:** A structured onboarding form covering data handling, access scope, certifications (SOC 2, ISO 27001), subprocessor disclosure, and breach notification procedures.
- **Risk Scoring Model:** A weighted scoring rubric that rates vendors across five domains: data sensitivity, access level, business criticality, compliance posture, and financial stability. Outputs a composite risk tier (Critical, High, Medium, Low).
- **NIST CSF Control Mapping:** A crosswalk document linking each assessment question to the relevant NIST CSF subcategory, enabling gap analysis and evidence tracking.
- **Risk Register Template:** A living document format for tracking vendor risk decisions, remediation actions, review cadences, and risk acceptance sign-offs.
- **Tiered Review Schedule:** A policy document defining reassessment frequency by risk tier, escalation paths, and criteria for offboarding a vendor.
- **Sample Assessment Reports:** Two anonymised worked examples showing a High-risk SaaS vendor and a Low-risk professional services firm assessed through the full framework.

## Skills & Tools Demonstrated

**GRC Practices**
- Vendor and third-party risk management (TPRM)
- Risk categorisation and tiering
- NIST CSF alignment and control mapping
- GRC documentation and policy writing

**Frameworks & Standards**
- NIST Cybersecurity Framework (CSF) v1.1 and v2.0
- SOC 2 Type II scoping awareness
- ISO 27001 Annex A control references

**Tooling**
- `Excel` / `Google Sheets` for scoring model and risk register templates
- `Markdown` for all policy and procedural documentation
- `Python` (`pandas`) for scoring logic automation and report generation
- `draw.io` for workflow diagrams
- `Git` / `GitHub` for version control and artefact management

## Architecture & Approach

The framework follows a linear lifecycle with three discrete phases: intake, assessment, and ongoing management. Vendors enter through a standardised questionnaire. Responses feed a scoring model that assigns a risk tier. That tier then determines the depth of the assessment, the required evidence, and the review frequency.

I deliberately separated the scoring logic from the templates so the rubric can be updated without invalidating historical records. The Python scripts are optional helpers, not a dependency. A team without engineering support can run the entire framework using only the spreadsheet and Markdown artefacts.

```text
Vendor Onboarding Request
        |
        v
  Intake Questionnaire
        |
        v
  Scoring Model (weighted rubric)
        |
        v
  Risk Tier Assigned (Critical / High / Medium / Low)
        |
     ___|___________________________________
    |           |            |             |
 Critical     High        Medium          Low
 Full audit  Deep review  Standard     Self-attest
 + legal     + controls   review       + annual
 review      validation               reassessment
        |
        v
  Risk Register Entry + Remediation Tracking
        |
        v
  Scheduled Reassessment (tier-based cadence)
```

## Suggested Repository Structure

```text
vendor-risk-framework/
├── README.md
├── docs/
│   ├── vendor-risk-policy.md
│   ├── tiered-review-schedule.md
│   └── nist-csf-control-mapping.md
├── templates/
│   ├── vendor-intake-questionnaire.xlsx
│   ├── risk-scoring-model.xlsx
│   └── risk-register-template.xlsx
├── scripts/
│   ├── score_vendor.py
│   └── generate_report.py
├── sample-assessments/
│   ├── sample-high-risk-saas-vendor.md
│   └── sample-low-risk-professional-services.md
├── diagrams/
│   └── assessment-workflow.drawio
└── requirements.txt
```

## What This Demonstrates to Employers

- **Shows ability to own the full TPRM lifecycle**, from vendor intake through risk scoring, documentation, and scheduled reassessment, with minimal oversight.
- **Demonstrates familiarity with NIST CSF** as a practical control mapping tool, not just a theoretical reference, including the ability to align vendor evidence to specific subcategories.
- **Shows strong GRC documentation skills**, producing audit-ready artefacts that legal, security, and procurement teams can act on immediately.
- **Demonstrates risk-tiering judgement**, applying a weighted, repeatable model that produces defensible, consistent outcomes across diverse vendor types.
- **Shows cross-functional awareness**, designing outputs that serve multiple stakeholders including compliance, finance, and engineering without requiring translation.
- **Demonstrates the ability to scale a process**, separating policy from tooling so the framework works for a two-person team and a fifty-vendor portfolio alike.

## Getting Started

**Prerequisites:** Python 3.9+, `pandas`, and a spreadsheet application. Clone the repo and install the Python dependencies.

```bash
git clone https://github.com/your-username/vendor-risk-framework.git
cd vendor-risk-framework
pip install -r requirements.txt
```

To score a vendor using the provided sample input:

```bash
python scripts/score_vendor.py --input templates/vendor-intake-questionnaire.xlsx --output results/vendor-score.csv
```

All policy documents and templates in `docs/` and `templates/` are standalone and require no tooling to use.
