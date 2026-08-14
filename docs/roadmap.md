# Project Synapse Roadmap

## Objective

Convert the source-backed academic work into a publicly reproducible, safely documented graduation-project artifact. Progress is governed by evidence states, not dates.

## Evidence states

| State | Meaning |
|---|---|
| Source-backed | stated in the White Paper, academic report, or development plan |
| Implemented | code/configuration exists in the reviewed tree |
| Integrated | components exchange expected data in a controlled test |
| Measured | results and method are retained |
| Publicly reproducible | a reviewer can rerun the result from sanitized artifacts |
| Production-validated | outside the current claim boundary unless separately proven |

## Gate 1 — identity and source hierarchy

- [x] define Project Synapse as the graduation project;
- [x] separate it from SOCRoot;
- [x] identify White Paper v2.0 as concept/architecture source;
- [x] identify the 2025–2026 academic report as delivery/results source;
- [x] preserve Google Drive as the original-file layer and GitHub as the sanitized public engineering layer.

**Gate result:** complete.

## Gate 2 — public architecture baseline

- [x] document enterprise and PSM boundaries;
- [x] publish the stream-detect-store path;
- [x] document the controlled CVE lifecycle as a separate planned workflow;
- [x] label enterprise scale as a target, not a result;
- [ ] publish component/version inventory and interface schemas.

**Gate result:** substantially complete; contracts remain.

## Gate 3 — PSM reproducibility package

The academic report states that PSM is implemented and measured. GitHub must now make that evidence independently reviewable.

- [ ] sanitized event generator and deterministic seed;
- [ ] Docker Compose/environment specification;
- [ ] pinned component versions;
- [ ] detection rules and expected outputs;
- [ ] benchmark command and raw result format;
- [ ] confusion-matrix labels and calculation;
- [ ] clean-environment reproduction guide.

**Gate:** reported results can be rerun without private data or hidden configuration.

## Gate 4 — CVE lab workflow

- [ ] select authorized, technically meaningful CVEs;
- [ ] define an isolated lab template;
- [ ] verify `synapse init`, `exploit`, `patch apply`, `verify`, `evidence`, and `report`;
- [ ] capture pre-exploit baseline and post-patch retest;
- [ ] produce tamper-evident evidence with hashes and timestamps;
- [ ] document teardown and rollback.

**Gate:** one CVE completes exploit → detect → patch → verify → evidence → report safely and reproducibly.

## Gate 5 — expanded hybrid detection

- [ ] add versioned rules for lateral movement, persistence, and credential access;
- [ ] document false-positive and evasion cases;
- [ ] build a labeled validation set;
- [ ] compare against a simple baseline;
- [ ] evaluate an explainable anomaly method only after data-quality checks;
- [ ] add analyst feedback and drift monitoring.

**Gate:** broader coverage improves measured utility without hiding uncertainty.

## Gate 6 — resilience and scale-out validation

- [ ] multi-node Kafka/OpenSearch/Spark test;
- [ ] replay, duplicate, and idempotency tests;
- [ ] connector-failure and back-pressure exercises;
- [ ] backup, restore, and rollback;
- [ ] resource and latency measurements by stage;
- [ ] capacity model reconciled against new evidence.

**Gate:** scale claims cite retained measurements rather than linear-scaling assumptions alone.

## Gate 7 — graduation and portfolio package

- [ ] architecture and data-flow visuals;
- [ ] concise recruiter-facing project summary;
- [ ] technical setup and verification guide;
- [ ] benchmark and analytics artifact;
- [ ] CVE workflow evidence;
- [ ] limitations, ethics, privacy, and responsible-use statement;
- [ ] presentation narrative and demo fallback;
- [ ] evidence index linking each major claim to its artifact.

## Immediate priorities

1. publish the PSM reproducibility package;
2. publish component versions and event/finding schemas;
3. validate one controlled CVE workflow;
4. create machine-readable benchmark output;
5. add architecture and result figures with sanitized evidence.
