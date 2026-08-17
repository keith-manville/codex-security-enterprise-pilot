# Customer Presentation Outline

## Slide 1 — Vulnerability Management Has a Judgment Bottleneck

Enterprise security teams already generate large volumes of findings.

The scarce resource is experienced security judgment:

- Is it real?
- Is it exploitable?
- Does it matter here?
- What is the safest remediation?

**Message:** The opportunity is not simply finding more vulnerabilities. It is reducing the effort required to reach a trustworthy remediation decision.

## Slide 2 — Why This Is Getting Harder

Software supply chains, CI/CD complexity, and AI-assisted security research are increasing the speed at which weaknesses can be identified and investigated.

Defenders need comparable improvements in investigation and remediation velocity.

**Message:** Increase security-engineering leverage without removing governance.

## Slide 3 — Where Codex Security Fits

Repository
→ context and security policy
→ Codex Security
→ discovery
→ evidence and validation
→ human review
→ remediation
→ existing engineering workflow

**Message:** Codex Security complements existing scanners, source-control controls, and AppSec teams.

## Slide 4 — Representative Workflow

Demonstration scenario:

A GitHub Actions release workflow permits a version tag to initiate publication of an official container image.

Attack path:

Unapproved commit
→ release tag
→ GitHub Actions
→ container build
→ official registry
→ downstream consumers

## Slide 5 — What Codex Security Discovered

Codex Security identified that repository-local release logic did not verify that the tagged commit came from the approved release branch before publication.

**Message:** The analysis extended beyond application source code into CI/CD and software-supply-chain logic.

## Slide 6 — Where AI Stopped and Enterprise Context Began

### Repository evidence

- `v*` tag triggers release automation
- tagged revision is checked out
- container publication is attempted

### Enterprise evidence still required

- who can create tags
- GitHub rulesets
- protected environments
- registry permissions
- downstream verification controls

**Message:** Repository context is powerful, but enterprise context determines actual risk.

## Slide 7 — Remediation Requires Layered Controls

Protected source
→ protected release tag
→ release validation
→ unprivileged build
→ immutable artifact
→ independent approval
→ credentialed publication

**Message:** Codex can recommend controls, but secure operation depends on both repository changes and enterprise governance.

## Slide 8 — Product Assessment

### Strongest Areas

- repository comprehension
- security reasoning
- attack-path analysis
- evidence generation
- remediation proposals

### Limitations

- important controls may exist outside the repository
- severity depends on deployment context
- findings and patches still require human review

### Appropriate Users

- AppSec
- Product Security
- Security Engineering
- Developers as remediation partners

## Slide 9 — Controlled Enterprise Pilot

Start with 5–10 representative repositories over three weeks.

Measure:

- finding quality
- analyst agreement
- investigation efficiency
- remediation quality
- review load
- operational fit
- scale and usage characteristics

**Recommendation:** Expand gradually only when the pilot demonstrates measurable security value and manageable human-review requirements.
