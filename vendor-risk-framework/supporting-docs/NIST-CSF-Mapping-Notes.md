# NIST CSF 2.0 Mapping Notes

## Why map to NIST CSF instead of writing a generic checklist

A self-authored security checklist only reflects one analyst's judgment about what matters. Mapping every questionnaire item to a recognized framework does three things a generic checklist can't:

1. **Comparability.** A vendor's Govern-function score can be benchmarked against how their own SOC 2 or ISO 27001 report frames governance controls, because both ultimately trace back to the same underlying control objectives.
2. **Defensibility.** When Legal, Procurement, or an external auditor asks "why these questions," the answer is "these trace to NIST CSF 2.0," not "an analyst's judgment call."
3. **Coverage.** Structuring questions around all six Functions prevents the common failure mode of an assessment that is 80% Protect-function questions (encryption, MFA, access control) and blind to Govern, Detect, Respond, and Recover — the functions that actually predict how a vendor behaves *during* and *after* an incident, not just whether they have controls on paper.

## The six Functions, applied to vendor risk

| Function | What it tests in a vendor context |
|----------|-----------------------------------|
| Govern | Does the vendor have a security program with actual ownership and executive visibility, or is security nobody's job? |
| Identify | Does the vendor know what it has and what could go wrong — asset inventory, data flows, subcontractor visibility? |
| Protect | Are the baseline technical controls in place — encryption, MFA, least privilege, patching, training? |
| Detect | Would the vendor actually notice a compromise, or find out from a customer / the press? |
| Respond | If something goes wrong, does the vendor have a plan, and are they contractually obligated to tell us fast enough to matter? |
| Recover | Can the vendor actually restore service and data, and have they proven it — or is "we have backups" an untested assumption? |

## Design choice: nested tiers, not three separate question sets

Each tier's questionnaire is a strict subset of the tier above it (Tier 3 ⊂ Tier 2 ⊂ Tier 1), built by taking the highest-priority domain within each Function first. This means:

- A Tier 3 vendor that gets re-tiered to Tier 2 after a scope change doesn't start its assessment history over — its existing 15 answers are already part of the 30-question set.
- Cross-tier reporting (e.g., "% of all vendors enforcing MFA") stays apples-to-apples because the underlying question text doesn't change between tiers, only the number of domains covered.

## Domain-to-Function allocation (Tier 1, 60 questions)

10 domains per Function, chosen to reflect what a payments-and-ticketing marketplace actually needs from its vendors: heavier weighting (Risk Weight 3) on encryption, MFA, least privilege, and breach notification SLA — the controls most directly tied to PCI DSS obligations and customer data exposure. Lighter weighting (Risk Weight 1) on maturity signals like awareness training cadence and log retention, which matter but don't singlehandedly prevent a breach.

## Sources

- NIST Cybersecurity Framework (CSF) 2.0, published February 2024 — the six Functions (Govern, Identify, Protect, Detect, Respond, Recover) and their intent as summarized on the official NIST CSF 2.0 resource page.
- PCI DSS v4.0 control themes (encryption, access control, monitoring, incident response) informed the Risk Weight assigned to Protect- and Respond-function questions relevant to payment processors.
