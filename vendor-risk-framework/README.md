# Vendor Risk Assessment Framework

A complete third-party risk management framework built to NIST CSF 2.0, covering vendor tiering, risk questionnaires, scoring rubrics, risk register management, and executive reporting. Built as a portfolio project simulating the vendor risk lifecycle a GRC Analyst II would own at a high-transaction-volume marketplace like StubHub, spanning payment processors, cloud infrastructure, analytics platforms, integration partners, and staffing vendors.

## Documents

- `VRA-Framework-Policy.pdf`: Scope statement, vendor landscape, tiering model summary, scoring methodology, risk acceptance and escalation criteria, risk acceptance statement template, and governance roles.
- `VRA-Tiering-Model.xlsx`: Tiering criteria and decision tree (Sheet 1), plus a 10-vendor risk register with live formulas, data validation, and conditional formatting (Sheet 2).
- `VRA-Questionnaire.xlsx`: Three tiered questionnaires (60 / 30 / 15 questions) mapped to all six NIST CSF 2.0 Functions, plus a scoring key and risk rating band reference.
- `VRA-Executive-Summary-Template.pdf`: Quarterly reporting template, populated with sample findings from the fictional vendor register.
- `supporting-docs/NIST-CSF-Mapping-Notes.md`: Rationale for how questionnaire domains map to NIST CSF 2.0 Functions.

## Framework Design Decisions

- **Three-tier model** based on data sensitivity and operational criticality, with a decision tree an analyst can apply in under a minute at vendor intake.
- **Questions mapped to all six NIST CSF 2.0 Functions** (Govern, Identify, Protect, Detect, Respond, Recover) rather than a generic checklist, so results are comparable to how auditors and enterprise security teams already think about risk.
- **Nested questionnaire depth**: the Tier 3 lightweight questionnaire is a strict subset of Tier 2, which is a strict subset of Tier 1 — so a vendor's assessment history stays comparable even if its tier changes.
- **Scores translate directly into decisions**: every score band (Critical/High/Medium/Low) maps to a specific onboarding, remediation, and escalation requirement in the policy document, not just a color on a dashboard.
- **Risk register as a living dashboard**: conditional formatting on both the numeric score and the derived risk rating means any stakeholder can scan the sheet and see where attention is needed without reading every row.

## How to Use This Framework

1. New vendor comes in → apply the Tiering Decision Tree (`VRA-Tiering-Model.xlsx`, Sheet 1) → assign Tier 1, 2, or 3.
2. Send the matching questionnaire tab from `VRA-Questionnaire.xlsx`.
3. Score responses using the `Scoring-Key` tab; the resulting Vendor Security Score determines the Risk Rating via `Risk Rating Bands`.
4. Log the vendor, score, and findings in the `Vendor Inventory` tab of `VRA-Tiering-Model.xlsx`.
5. Apply the required action for that risk band from `VRA-Framework-Policy.pdf`, Section 5.
6. Roll up the register into `VRA-Executive-Summary-Template.pdf` each quarter.
