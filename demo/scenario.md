# Demo Scenario

## Customer

A large enterprise software organization with:

- GitHub Enterprise
- Mature CI/CD
- Existing SAST, SCA, and vulnerability-management tooling
- A centralized AppSec team
- Hundreds or thousands of repositories
- Container-based software delivery

## Customer Problem

The organization already has tools that generate security findings.

The bottleneck is experienced human judgment:

- Is the finding actually exploitable?
- Does it matter in this environment?
- What evidence supports the severity?
- What is the safest remediation?
- Which controls belong in code versus the surrounding platform?

## Selected Workflow

**Vulnerability Operations**

The demonstration focuses on a software supply-chain risk in a GitHub Actions release workflow.

A release tag can trigger publication of an official container image.

Codex Security is used to:

1. Understand the repository and security policy.
2. Discover the candidate vulnerability.
3. Trace the attack path.
4. Separate repository evidence from external enterprise assumptions.
5. Reassess severity based on available evidence.
6. Propose a minimal remediation.
7. Identify residual risks and required enterprise controls.

## Attack Path

Unapproved commit  
→ release tag  
→ GitHub Actions workflow  
→ container build  
→ privileged publication credentials  
→ official container registry  
→ downstream consumers

## Key Enterprise Question

The repository proves that a tag triggers a privileged release workflow.

It does not prove who is authorized to create release tags or what external GitHub controls exist.

This creates an important distinction between:

### Repository-proven facts

- A `v*` tag triggers the release workflow.
- The tagged revision is checked out.
- The workflow can build and publish an official container image.
- No repository-local ancestry validation exists before publication.

### Enterprise context still required

- Tag creation permissions
- GitHub rulesets
- Branch protection
- Environment approvals
- Registry permissions
- Artifact-signing controls
- Consumer verification policies

## Human Oversight

Human review remains required for:

- validating enterprise context,
- dispositioning the finding,
- determining severity,
- approving remediation,
- validating GitHub and registry controls,
- and approving release or deployment.

## Core Lesson

Codex Security can accelerate the path from a potential repository-level security issue to evidence-backed analysis and remediation.

It should not be treated as a replacement for enterprise identity, source-control governance, CI/CD policy, or human security judgment.
