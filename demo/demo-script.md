# Demo Script

## 0:00–0:45 — Set the customer context
- Large enterprise with GitHub Enterprise and mature AppSec.
- Existing scanners already generate findings.
- Codex Security can triage an existing backlog against repository evidence; this demo follows the complementary new-discovery path.
- The bottleneck is validating what is real, understanding impact, and getting to a safe fix.

## 0:45–1:30 — Introduce the repository
- Show the repo in Codex.
- Explain that Codex Security first understands repository context and security policy.
- Mention that this repo contains application code, CI/CD, and release workflows.

## 1:30–2:30 — Show the finding
- Open the supply-chain finding:
  “Tags directly authorize publication.”
- Explain the attack path:
  unapproved commit → release tag → GitHub Actions → container build → official registry.

## 2:30–3:30 — Challenge the finding
- Show Codex separating:
  - repository-proven facts
  - enterprise assumptions
- Highlight missing context:
  tag permissions, rulesets, environment approvals, registry controls.

## 3:30–4:15 — Show severity recalibration
- Explain that the original finding was High.
- After investigation, Codex recalibrated it to conditional Medium pending external evidence.
- Emphasize that the model did not overclaim certainty.

## 4:15–5:15 — Show remediation
- Show the proposed release validation check.
- Explain that the workflow verifies the tagged commit came from the approved release branch before allowing publication.
- Then show the residual risk: this check may not be sufficient on its own if an attacker can also modify the release workflow or bypass surrounding GitHub controls.

## 5:15–6:15 — Show layered enterprise controls
- Protected source branch
- Protected release tags
- Build/publish separation
- Protected environment
- Short-lived credentials
- Signed immutable artifacts
- Independent human approval

## 6:15–7:00 — Close with the product point of view
- Codex Security is strong at repository understanding, backlog triage, attack-path reasoning, validation evidence, proof-gap identification, and focused remediation guidance.
- It still needs enterprise context that lives outside the repo.
- Human security judgment remains essential for risk disposition and production approval.
- Pilot narrowly, measure quality, then scale.
