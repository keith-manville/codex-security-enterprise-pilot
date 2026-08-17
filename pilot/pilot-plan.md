# Codex Security Enterprise Pilot Plan

## Objective

Evaluate whether Codex Security can improve an enterprise vulnerability-management workflow by helping AppSec teams triage existing findings, discover new repository-level vulnerabilities, validate uncertain findings when needed, and remediate accepted findings while preserving human oversight.

The pilot is designed to answer a practical question:

> Can Codex Security reduce the human effort required to move from a potential security issue to an evidence-backed remediation decision?

## Pilot Scope

Run a controlled three-week evaluation using a small set of representative repositories.

Recommended scope:

- 5–10 representative repositories
- Mix of internet-facing and internal applications
- Mix of languages and frameworks
- At least one application with a complex CI/CD pipeline
- At least one dependency-heavy application
- At least one containerized application
- Repositories with known historical security findings where possible

The pilot should not begin with an organization-wide rollout.

### Data and Access Assumptions

- Only repositories explicitly authorized for assessment are included.
- Repository access follows existing enterprise identity, role, and workspace controls.
- Pilot participants receive only the permissions required for their role.
- Sensitive repository and security data should remain subject to the customer's existing governance and handling requirements.

## Participants

### Application Security / Product Security

Primary operators and reviewers.

Responsibilities:

- Review repository context and security assumptions
- Review Codex Security findings
- Validate severity and exploitability
- Approve or reject remediation recommendations
- Record evaluation results

### Development Teams

Responsibilities:

- Review proposed fixes
- Validate application behavior
- Run existing tests
- Approve code changes through normal pull-request workflows

### Platform / DevOps / Security Engineering

Responsibilities:

- Validate CI/CD and source-control assumptions
- Confirm repository and organization-level controls
- Review release and credential-management implications

## Week 1 — Establish Baseline and Ground Truth

### Goals

- Select pilot repositories
- Define scope
- Establish known security context
- Identify human reviewers
- Capture baseline workflow metrics

### Activities

1. Select 5–10 representative repositories.
2. Review each repository's security policy and ownership.
3. Document available architectural and deployment context.
4. Collect existing security evidence where available:
   - historical human-validated AppSec findings
   - penetration-test results
   - previously remediated vulnerabilities
   - previous vulnerability tickets
   - SAST and SCA findings as comparison data
5. Establish a known-positive evaluation set from previously human-validated vulnerabilities and resolved security findings where available. Treat existing scanner findings as comparison data unless independently validated.
6. Record the current human process for:
   - investigation
   - severity assignment
   - remediation
   - developer handoff
7. Define pilot success criteria before running Codex Security.

### Human Approval Point

AppSec confirms repository scope, known context, and evaluation criteria.

## Week 2 — Controlled Codex Security Assessment

### Goals

Evaluate finding quality and investigation usefulness.

### Activities

1. Run Codex Security against each selected repository.
2. Review repository context and threat-model assumptions.
3. Capture candidate findings.
4. For each selected finding, record:
   - finding description
   - severity
   - evidence
   - attack path
   - validation status
   - assumptions
5. Compare Codex Security findings against known ground truth and existing tooling.
6. Have AppSec reviewers independently disposition selected findings.

### Reviewer Disposition

Each finding should be classified as:

- Confirmed
- High confidence
- Plausible / requires more evidence
- Likely false positive
- Not applicable
- Known / accepted risk

### Human Approval Point

Codex Security does not independently decide enterprise risk acceptance.

AppSec retains responsibility for final finding disposition and severity.

## Week 3 — Remediation and Operational Evaluation

### Goals

Determine whether Codex Security improves the path from finding to safe remediation.

### Activities

1. Select a representative subset of validated findings.
2. Ask Codex Security to propose remediation.
3. Review:
   - files changed
   - scope of change
   - security impact
   - possible regressions
   - tests added or modified
4. Run normal CI and security checks.
5. Have developers review the proposed remediation.
6. Measure how much human modification is required.
7. Compare the Codex-assisted workflow to the organization's existing process.
8. Conduct a final pilot review with AppSec, engineering, and platform stakeholders.
9. For selected accepted findings, test portable export or approval-gated issue preparation as part of the handoff workflow.

### Human Approval Points

Humans retain responsibility for:

- accepting the finding
- assigning severity
- approving remediation
- approving pull requests
- approving release or deployment

No autonomous production changes are included in the pilot.

## Evaluation Metrics

### 1. Finding Quality

Measure the percentage of surfaced findings that AppSec considers actionable.

### 2. Analyst Agreement

Measure how often human reviewers agree with Codex Security's:

- finding validity
- severity
- attack-path explanation

### 3. Investigation Efficiency

Measure:

> Human investigation minutes per validated actionable vulnerability.

Compare this with the existing workflow.

### 4. Remediation Quality

Measure:

- percentage of proposed fixes accepted
- amount of developer editing required
- CI / test success rate
- regression rate

### 5. Novel Security Value

Record whether Codex Security discovers meaningful issues that existing tools or previous reviews did not identify.

### 6. Operational Fit

Evaluate whether Codex Security outputs can fit naturally into:

- AppSec review
- GitHub workflows
- pull-request review
- vulnerability-management processes
- existing security governance

### 7. Review Load

Measure:

- analyst minutes required to review Codex Security output per repository
- analyst minutes required per actionable finding
- number of findings requiring deeper manual investigation

### 8. Scale and Usage

Measure:

- scan duration by repository size and complexity
- reviewer workload
- concurrency or throughput constraints
- usage and cost characteristics where available

The objective is to determine whether the workflow can scale without exceeding available AppSec review capacity.

## Safety and Human Oversight

The pilot treats Codex Security as a security-engineering assistant, not an autonomous decision-maker.

Required controls include:

- Authorized repositories only
- Human review of security context
- Human disposition of findings
- Human review of proposed fixes
- Existing CI and security checks remain enforced
- Existing pull-request approval remains enforced
- No autonomous merges
- No autonomous production deployments

## Key Limitations to Evaluate

The pilot should explicitly assess situations where important context exists outside the repository, including:

- GitHub permissions and rulesets
- cloud configuration
- runtime controls
- identity and access management
- deployment topology
- registry permissions
- compensating controls

These limitations should be treated as evaluation findings, not hidden.

The pilot does not assume Codex Security replaces the customer's upstream normalization or deduplication pipeline. Those capabilities remain part of the surrounding vulnerability-management workflow unless explicitly validated.

## Exit Criteria

At the end of the pilot, the customer should be able to answer:

1. Does Codex Security produce useful, actionable findings?
2. Does it reduce AppSec investigation effort?
3. Does it improve remediation speed or quality?
4. Where does it still require significant human or external context?
5. Which teams should own the workflow?
6. What governance is required before broader adoption?
7. Should usage expand beyond the pilot repositories?
8. Can the organization operate Codex Security at the next scale tier without exceeding available AppSec review capacity?

## Scale-Out Path

If the controlled pilot meets its quality and review-load thresholds, evaluate scale in stages:

1. **Security Workbench / focused repository reviews** for analyst-led onboarding and investigation.
2. **CLI bulk scans** against a controlled repository inventory pinned to exact revisions.
3. **Diff-focused CI scanning** with structured artifacts such as SARIF.
4. **Selective enforcement** only after finding quality, false-positive rates, reviewer capacity, and ownership are proven.

Bulk or CI adoption should not remove the human decision boundaries established in this pilot.

## Expansion Decision

Expand the deployment only if the customer observes:

- acceptable finding quality
- measurable analyst-efficiency improvement
- useful remediation output
- manageable review overhead
- no unacceptable regression or governance risk
- clear ownership between AppSec, development, and platform teams

The next phase should expand gradually by repository risk tier rather than immediately enabling every repository.
