# Pilot Success Criteria

## Purpose

These criteria define what must be true before recommending broader adoption of Codex Security.

The pilot is successful only if Codex Security demonstrates measurable security value without creating unacceptable review burden or weakening existing human approval controls.

## 1. Finding Quality

### Success

- AppSec reviewers consider a meaningful percentage of reviewed findings actionable.
- Findings include sufficient evidence for a reviewer to understand the affected code or configuration, attack path, and assumptions.
- False positives do not create an unsustainable review burden.

### Warning Sign

- Reviewers routinely cannot reproduce or substantiate findings.
- Findings require substantial manual investigation before they become useful.

## 2. Analyst Efficiency

### Success

Codex Security reduces:

> Human investigation minutes per validated actionable vulnerability.

The pilot should compare this metric against the customer's existing AppSec workflow.

### Warning Sign

The review effort required to understand Codex Security output exceeds the effort saved during investigation.

## 3. Analyst Agreement

### Success

Human reviewers generally agree with Codex Security on:

- finding validity,
- attack-path reasoning,
- affected components,
- and remediation direction.

Severity disagreement should be recorded separately because enterprise context may materially affect risk.

## 4. Remediation Quality

### Success

For validated findings:

- proposed fixes address the identified root cause,
- changes are reasonably scoped,
- normal tests and CI checks pass,
- and developers can accept the remediation with limited modification.

## 5. Enterprise Context Handling

### Success

Codex Security clearly distinguishes:

- repository-proven evidence,
- model inference,
- and enterprise context that must be validated externally.

## 6. Human Oversight

### Success

The pilot preserves human authority over:

- finding disposition,
- severity,
- remediation approval,
- pull-request approval,
- release approval,
- and production deployment.

## 7. Operational Fit

### Success

AppSec and development teams can incorporate Codex Security into existing repository and review workflows without creating a parallel security operating model.

## 8. Scalability

### Success

The customer can estimate:

- scan duration,
- reviewer demand,
- findings per repository,
- cost or usage characteristics,
- and expected AppSec capacity at the next rollout tier.

## Pilot Exit Decision

### Expand

Expand to the next repository risk tier when:

- finding quality is acceptable,
- analyst-efficiency improvements are measurable,
- remediation output is useful,
- review load is manageable,
- human approval remains intact,
- and ownership is clear.

### Continue Evaluating

Continue the pilot when results are promising but additional evidence is required.

### Stop

Do not expand when:

- finding quality is consistently poor,
- review effort outweighs value,
- remediation introduces unacceptable risk,
- or governance requirements cannot be satisfied.
