# Codex Security Evaluation Scorecard

Use this scorecard for each representative repository or selected finding during the enterprise pilot.

## Repository Information

**Repository:**  
**Application / Service:**  
**Business Criticality:**  
**Reviewer:**  
**Date:**  
**Codex Security Scan Type:**  

## Finding

**Finding Title:**  
**Initial Severity:**  
**Final Human Severity:**  

## 1. Finding Validity

Select one:

- Confirmed
- High confidence
- Plausible / needs additional evidence
- Likely false positive
- Not applicable
- Known / accepted risk

**Reviewer Notes:**

## 2. Evidence Quality

Score from 1–5.

**Score:**  

Consider:

- affected code or configuration,
- attack path,
- preconditions,
- supporting evidence,
- and clarity of assumptions.

**Reviewer Notes:**

## 3. Enterprise Context

### Repository-Proven Facts

Record what Codex Security established directly from the repository.

### External Context Required

Record any required information not available in the repository, such as:

- IAM
- GitHub rulesets
- runtime configuration
- cloud controls
- networking
- registry permissions
- compensating controls

## 4. Severity Agreement

Did the human reviewer agree with Codex Security's initial severity?

- Yes
- Partially
- No

**Reason for difference:**

## 5. Investigation Efficiency

**Approximate analyst review time:**  

**Estimated time using existing process:**  

**Did Codex Security reduce investigation effort?**

- Yes
- No
- Unclear

## 6. Remediation Quality

Was remediation requested?

- Yes
- No

If yes:

**Remediation assessment:**

- Acceptable as proposed
- Acceptable with minor edits
- Requires substantial changes
- Not appropriate

**Did normal tests / CI pass?**

- Yes
- No
- Not tested

**Reviewer Notes:**

## 7. Human Approval Required

Identify required human checkpoints:

- Threat-model / context review
- Finding disposition
- Severity assignment
- Remediation review
- Pull-request approval
- Release approval
- Production deployment approval
- Other

## 8. Product Assessment

Score each area from 1–5.

| Area | Score | Notes |
|---|---:|---|
| Repository understanding | | |
| Security reasoning | | |
| Evidence quality | | |
| Validation usefulness | | |
| Remediation quality | | |
| Enterprise-context awareness | | |
| Reviewer usability | | |
| Operational fit | | |

## 9. Final Reviewer Decision

Would you want Codex Security used on similar repositories?

- Yes
- Yes, with conditions
- More evaluation required
- No

**Conditions / rationale:**

## 10. Key Learning

**What Codex Security did particularly well:**

**Where human judgment materially changed the result:**

**Most important limitation observed:**
