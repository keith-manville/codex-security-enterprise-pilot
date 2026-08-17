# Codex Security Enterprise Pilot

## Purpose

This repository is a customer-facing evaluation framework for assessing Codex Security in an enterprise vulnerability-management workflow.

The goal is to demonstrate how Codex Security can help security teams move from either existing security findings or new repository-native discovery to evidence-backed triage, validation when needed, remediation guidance, and human-reviewed engineering actions.

## Customer Scenario

A large enterprise operates hundreds or thousands of software repositories with mature CI/CD and existing security tooling.

The security team already receives findings from multiple sources, but experienced AppSec engineers remain the bottleneck for:

- determining whether findings are exploitable,
- understanding application-specific impact,
- prioritizing remediation,
- evaluating proposed fixes,
- and deciding when a change is safe to approve.

The pilot evaluates whether Codex Security can improve that workflow without removing human ownership of security decisions.

## Selected Workflow

**Vulnerability Operations**

This project evaluates two complementary Codex Security paths:

1. **Existing backlog triage** — review supplied findings against repository evidence, identify proof gaps, and prioritize follow-up.
2. **New discovery** — perform repository-aware vulnerability discovery, validation or other checks, impact/path analysis, and remediation planning.

The live demonstration emphasizes software supply-chain and release-pipeline risk through the new-discovery path. Existing scanner findings remain part of the broader vulnerability-operations design.

## Core Thesis

Codex Security should be evaluated as a security-engineering force multiplier, not as an autonomous security control.

A safe enterprise operating model is:

Existing findings **or** authorized repository
→ Codex Security triage / discovery
→ Evidence + proof gaps
→ Validation when needed
→ Human security review
→ Focused remediation
→ CI / testing
→ Human approval
→ Deployment, release, or approval-gated issue handoff

## What This Repository Contains

- `demo/` — customer scenario and demo walkthrough
- `architecture/` — reference workflow and human decision boundaries
- `pilot/` — pilot plan, success criteria, and evaluation scorecard
- `evidence/` — screenshots and selected Codex Security outputs
- `presentation/` — customer-facing presentation outline

## Evaluation Focus

The pilot is designed to answer six questions:

1. Where does Codex Security work well?
2. What are its limitations?
3. Who are the appropriate users?
4. How does the workflow scale?
5. Where is human oversight required?
6. Is the product suitable for enterprise security workflows?

## Human Oversight Principle

Codex Security can assist with backlog triage, discovery, investigation, validation evidence, proof-gap identification, remediation planning, and structured handoff.

Humans retain responsibility for:

- enterprise-context validation,
- risk disposition,
- severity decisions,
- deciding when additional runtime validation is required,
- patch review,
- source-control and CI/CD governance,
- and production or release approval.

## Product Boundary

The original vulnerability-operations scenario includes normalization and deduplication. This pilot does not assume Codex Security replaces the customer's upstream vulnerability-management data pipeline.

Existing normalization and deduplication remain in the surrounding vulnerability-management workflow unless explicitly validated during the pilot.

## Current Demonstration Scenario

The initial demonstration examines a software supply-chain risk in a GitHub Actions release workflow where a release tag can initiate publication of an official container image.

The exercise shows how Codex Security:

- identifies the attack path,
- separates repository evidence from external enterprise assumptions,
- recalibrates severity when additional context is considered,
- proposes a focused remediation,
- identifies remaining proof gaps,
- and identifies the surrounding controls required for a complete enterprise solution.

## Scale-Out Path

A successful pilot can progress from:

**Security Workbench / focused repository review**
→ **CLI bulk scans against pinned repository revisions**
→ **diff-focused CI scanning and SARIF export**
→ **selected enforcement only after quality and operating thresholds are proven**

## Training and Evidence Note

OWASP Juice Shop was used as an authorized, deliberately vulnerable training repository to learn the Codex Security workflow and generate the initial evidence artifact.

It is not presented as a representative enterprise workload. The customer-facing submission uses the workflow and lessons learned to illustrate an enterprise evaluation methodology.

## Disclaimer

This repository is a demonstration project. It is not an official OpenAI product, reference architecture, or supported implementation.

## Status

Submission package in development. Core narrative, demo, architecture, pilot plan, success criteria, evaluation scorecard, and presentation outline are defined. Final screenshots, slide design, and video walkthrough remain.
