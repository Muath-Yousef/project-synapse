# Project Synapse Roadmap

## Objective

This roadmap moves Project Synapse from architecture documentation to a defensible graduation-project demonstration. Progress is controlled by evidence gates rather than dates or broad capability claims.

## Maturity vocabulary

| State | Meaning |
|---|---|
| Designed | responsibility and interface are documented |
| Implemented | code or configuration exists |
| Integrated | components exchange expected data in a controlled test |
| Measured | latency, resource use, errors, or analysis quality are recorded |
| Validated | acceptance criteria pass repeatedly with retained evidence |
| Production-ready | outside the current claim boundary unless separately proven |

## Phase 1 — identity and scope baseline

**Outcome:** the academic problem, project boundary, and success criteria are unambiguous.

- [x] define Project Synapse as the graduation project;
- [x] separate Project Synapse from SOCRoot's commercial identity;
- [x] publish safety and maturity boundaries;
- [x] define the public/private repository map.

**Gate:** README and documentation agree on purpose, ownership, and claim limits.

## Phase 2 — architecture and contracts

**Outcome:** a reviewer can trace the intended data and decision paths.

- [x] document the logical architecture and scale-out stages;
- [ ] publish the component/version inventory;
- [ ] define the normalized event schema;
- [ ] define finding, case, evidence, and approval contracts;
- [ ] record component rationale and alternatives.

**Gate:** every integration edge has an owner, schema, failure behavior, and evidence requirement.

## Phase 3 — reproducible POC

**Outcome:** a new reviewer can run the constrained environment using synthetic data.

- [ ] document prerequisites and setup;
- [ ] provide sanitized configuration examples;
- [ ] generate deterministic synthetic telemetry;
- [ ] validate ingestion, storage, search, and observability;
- [ ] retain expected and actual outputs.

**Gate:** setup succeeds from a clean environment and produces the documented baseline.

## Phase 4 — analytics evidence

**Outcome:** at least one security analysis is reproducible and explainable.

- [ ] define dataset scope, fields, exclusions, and quality checks;
- [ ] implement descriptive baseline analysis;
- [ ] evaluate a rule, statistical method, or ML method against a documented baseline;
- [ ] record false positives, false negatives, uncertainty, and limitations;
- [ ] link every conclusion to a versioned artifact.

**Gate:** another reviewer can reproduce the result from the documented input and method.

## Phase 5 — end-to-end security workflow

**Outcome:** one authorized synthetic alert moves through the complete controlled path.

- [ ] ingest and correlate the alert;
- [ ] generate a finding with evidence;
- [ ] enrich and open or update a case;
- [ ] require human approval for a sensitive action;
- [ ] execute dry-run or an explicitly approved lab action;
- [ ] retain audit, outcome, and rollback evidence;
- [ ] pass protected-target and approval-bypass negative tests.

**Gate:** all acceptance criteria pass repeatedly without unsafe side effects.

## Phase 6 — scalability and resilience

**Outcome:** the project can explain, with measurements, what must change beyond the POC.

- [ ] establish CPU, memory, storage, throughput, and latency baselines;
- [ ] test burst handling, retry, idempotency, and back-pressure;
- [ ] run connector-failure and recovery exercises;
- [ ] test backup, restore, and rollback;
- [ ] document bottlenecks and the distributed deployment plan.

**Gate:** scale and reliability claims cite retained measurements and known constraints.

## Phase 7 — graduation delivery package

**Outcome:** the project is reviewable as an academic and engineering artifact.

- [ ] architecture and data-flow diagrams;
- [ ] component and decision inventory;
- [ ] setup and verification guide;
- [ ] analytics artifact and interpretation;
- [ ] end-to-end demonstration evidence;
- [ ] limitations, ethics, privacy, and responsible-use statement;
- [ ] presentation narrative and demo fallback plan.

**Gate:** every major claim maps to a document, test, measurement, or clearly labeled future-work item.

## Immediate priorities

1. publish the component/version inventory and event schema;
2. define one deterministic synthetic end-to-end scenario;
3. create the first reproducible data-analysis artifact;
4. capture baseline performance and failure measurements;
5. assemble an evidence index for the graduation review.
