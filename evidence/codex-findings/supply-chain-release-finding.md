# Selected Codex Security Finding — Release Pipeline Supply-Chain Risk

## Context

This evidence summary is based on an authorized Codex Security assessment of OWASP Juice Shop used as a training and evaluation repository.

The goal of the exercise was not to present Juice Shop as an enterprise workload. It was to evaluate how Codex Security moves from repository context to a security finding, challenges its own assumptions, and proposes remediation.

## Initial Finding

Codex Security identified a release-pipeline path in which a `v*` tag could trigger a workflow that builds and publishes an official container image.

The initial assessment rated the finding High severity.

## Repository-Proven Facts

Codex Security established from the repository that:

- a matching release tag triggers the release workflow
- the tagged revision is checked out
- no repository-local check verifies that the tagged commit came from the approved release branch before publication
- the Docker publication path attempts to push an image to the project's documented distribution channel

## Enterprise Context Not Proven by the Repository

The repository alone could not establish:

- who is allowed to create release tags
- whether tag rulesets protect the `v*` namespace
- whether protected environments or independent approvals exist
- whether registry credentials are usable by the triggered workflow
- whether downstream consumers enforce signatures, provenance, or digest pinning

## Human Review and Severity Recalibration

After challenging the finding and separating repository facts from external enterprise assumptions, Codex Security recalibrated the issue from High to a conditional Medium pending additional evidence.

The key missing fact was whether a lower-trust actor could actually create the required release tag or otherwise bypass the approved release process.

## Proposed Remediation

Codex Security proposed adding a release validation check that verifies the tagged commit came from the approved release branch before allowing publication.

It also identified an important residual risk:

> A workflow-local validation check may not be sufficient on its own if an attacker can also modify the release workflow or bypass surrounding GitHub controls.

## Layered Enterprise Controls

A complete enterprise design should consider:

- protected and reviewed release branches
- protected release tags
- release validation before publication
- separation of build and publish
- protected environments and independent approval
- least-privilege or short-lived publication credentials
- signed immutable artifacts and provenance
- normal developer and security review gates

## Product Learning

### Strength

Codex Security connected repository code, GitHub Actions, release mechanics, credentials, and downstream distribution into a coherent attack path.

### Limitation

Final risk depended on enterprise controls outside the repository.

### Human Oversight

AppSec or platform security must validate external controls, disposition the finding, determine severity, and approve remediation.

### Enterprise Takeaway

Codex Security can accelerate the path from a potential repository-level security issue to evidence-backed analysis and remediation, while enterprise context and final risk decisions remain human responsibilities.
