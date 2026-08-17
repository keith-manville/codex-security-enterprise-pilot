# Customer Presentation Outline

## Slide 1 — Vulnerability Management Has a Judgment Bottleneck

### Executive message

Enterprise security teams do not lack findings. They lack enough experienced security judgment to investigate them all.

### Questions the workflow must answer

- Is the finding real?
- Is it exploitable?
- Does it matter in this environment?
- What is the safest remediation?

**Talk track:** The opportunity is not simply finding more vulnerabilities. It is reducing the effort required to reach a trustworthy remediation decision.

---

## Slide 2 — AI Changes the Economics of Security

### Executive message

AI can accelerate both vulnerability research and defensive security work.

### Why this matters

- Software and supply-chain complexity continues to increase.
- CI/CD and release infrastructure are part of the attack surface.
- AI lowers the effort required to investigate complex code paths.
- Defenders need comparable gains in investigation and remediation velocity.

**Message:** The response to AI-accelerated attackers should be AI-accelerated defenders, with controls.

---

## Slide 3 — Where Codex Security Fits

### Product architecture

```text
Repository + security policy
            ↓
\n       Codex Security
            ↓
Understand → Discover → Validate → Remediate
            ↓
        Human review
            ↓
Existing engineering / security workflow
```

### Key message

Codex Security complements existing scanners, AppSec teams, source-control controls, and CI/CD. It does not replace them.

---

## Slide 4 — Representative Vulnerability Operations Workflow

### Demonstration scenario

Software supply-chain risk in a release pipeline.

```text
Unapproved commit
      ↓
Release tag
      ↓
GitHub Actions
      ↓
Container build
      ↓
Official registry
      ↓
Downstream consumers
```

### Scope

This submission selects **Vulnerability Operations** and focuses the demonstration on repository-aware discovery, validation, prioritization, and remediation because Codex Security is the primary product being evaluated.

---

## Slide 5 — What Codex Security Found

Codex Security identified that:

- a matching release tag triggers privileged automation,
- the tagged revision is used for the build,
- the workflow can publish an official container image,
- and the repository did not itself verify that the tagged commit came through the approved release path.

### Key message

Codex reasoned beyond application source code into CI/CD and software-supply-chain logic.

### Visual

Use one screenshot from the Codex Security finding rather than a wall of text.

---

## Slide 6 — Where AI Stopped and Human Judgment Started

### Repository evidence

- A matching tag triggers the workflow.
- The tagged revision is checked out.
- A publication path exists.

### Enterprise context still required

- Who can create release tags?
- Are tags protected by rulesets?
- Are protected environments used?
- What permissions does the registry credential have?
- Are artifacts signed or promoted through another approval gate?

### What happened during review

The initial finding was rated High. After challenging the assumptions, Codex separated what the repository proved from what depended on external enterprise controls and recalibrated the finding to conditional Medium pending additional evidence.

#**Headline:** Repository context informs the analysis. Enterprise context determines the final risk decision.

---

## Slide 7 — Safe Remediation Requires Layered Controls

```text
Protected source
      ↓
Protected release tag
      ↓
Release validation
      ↓
Unprivileged build
      ↓
Immutable artifact
      ↓
Independent approval
      ↓
Credentialed publication
```

Codex proposed a release-validation control, then identified why that control might not be sufficient on its own if an attacker can modify the workflow or bypass surrounding GitHub controls.

**Key message:** AI can propose remediation, but secure operation depends on both repository controls and enterprise governance.

---

## Slide 8 — My Product Assessment

### Works well

- Repository comprehension
- Security reasoning
- Attack-path analysis
- Evidence generation
- Remediation proposals

### Limitations

- Important controls may exist outside the repository.
- Severity can depend heavily on deployment context.
- Validation is not proof of absence.
- Generated fixes still require normal engineering review.

### Appropriate users

- AppSec
- Product Security
- Security Engineering
- Developers as remediation partners

### Human oversight

- Context validation
- Finding disposition
- Severity assignment
- Patch review
- PR / release approval

---

## Slide 9 — Prove Value Before Production

### Three-week controlled pilot

- 5–10 representative repositories
- Dedicated AppSec reviewers
- Known-positive evaluation set
- Existing scanner data used as comparison evidence
- No autonomous merges or deployments

### Measure

- Finding quality
- Analyst agreement
- Human investigation time per actionable vulnerability
- Remediation acceptance
- Review load
- Operational fit
- Scale and usage characteristics

### Recommendation

Start narrow, prove finding quality and analyst leverage, preserve human approval, and expand by repository risk tier only when the evidence supports it.

---

## Story Arc

**Problem → Why now → Product fit → Real example → Discovery → Human judgment → Safe remediation → Product point of view → Pilot**
