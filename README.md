# Codex Security Enterprise Pilot

## Purpose

This repository is a customer-facing evaluation framework for assessing Codex Security in an enterprise vulnerability-management workflow.

The goal is to demonstrate how Codex Security can help security teams move from repository context and candidate findings to evidence-backed validation, remediation guidance, and human-reviewed engineering actions.

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

This project focuses on repository-aware vulnerability discovery, validation, prioritization, remediation planning, and human-reviewed fix workflows.

The demonstration emphasizes software supply-chain and release-pipeline risk.

## Core Thesis

Codex Security should be evaluated as a security-engineering force multiplier, not as an autonomous security control.

A safe enterprise operating model is:

Repository context  
→ Codex Security analysis  
→ Evidence and validation  
→ Human security review  
→ Proposed remediation  
→ CI / testing  
→ Human approval  
→ Deployment or release

## What This Repository Contains

- `demo/` — customer scenario and demo walkthrough
- `architecture/` — reference workflow and trust boundaries
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

Codex Security can assist with discovery, investigation, validation, and remediation planning.

Humans retain responsibility for:

- enterprise-context validation,
- risk disposition,
- severity decisions,
- patch review,
- source-control and CI/CD governance,
- and production or release approval.

## Current Demonstration Scenario

The initial demonstration examines a software supply-chain risk in a GitHub Actions release workflow where a release tag can initiate publication of an official container image.

The exercise shows how Codex Security:

- identifies the attack path,
- separates repository evidence from external enterprise assumptions,
- recalibrates severity when additional context is considered,
- proposes a minimal remediation,
- and identifies the surrounding controls required for a complete enterprise solution.

## Status

Work in progress.
