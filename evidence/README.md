# Evidence

This directory contains selected artifacts from the Codex Security learning and demonstration workflow.

The initial assessment used OWASP Juice Shop as an authorized, deliberately vulnerable training repository to learn and evaluate the Codex Security workflow.

## Evidence Included

- `codex-findings/supply-chain-release-finding.md` — sanitized summary of the selected release-pipeline finding and the human review process
- `screenshots/` — selected screenshots for the final demo and presentation

## Screenshots to Capture

Add 4–6 screenshots showing:

1. Repository architecture / context assessment
2. Security scan summary
3. Supply-chain release finding
4. Attack-path investigation and severity recalibration
5. Proposed release validation control
6. Layered enterprise control recommendation

## Evidence Handling

Do not publish:

- secrets or credentials
- sensitive customer data
- unnecessary raw scan transcripts
- local filesystem paths
- private repository information

The evidence should support the customer-facing story without requiring the audience to read an entire scan transcript.

## Narrative

Discovery  
→ investigation  
→ challenge assumptions  
→ human judgment  
→ remediation  
→ enterprise controls
