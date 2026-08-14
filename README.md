# Project Synapse

**Project Synapse is my cybersecurity graduation project.**

It explores how an open-source security stack can be combined with data analytics in a modular engineering architecture that can grow from a constrained prototype into a larger distributed deployment.

Project Synapse is **not SOCRoot** and it is not evaluated as a subscription business. Its success criteria are technical and academic: clear architecture, correct integration, reproducible evidence, explainable analysis, measured constraints, and a documented path to scale.

## Engineering objective

Build and document a hybrid SOC architecture that:

- uses reviewable, self-hostable, open-source components where practical;
- combines rule-based detection with data analysis and, where justified, statistical or ML techniques;
- makes the path from ingestion to storage, enrichment, detection, case handling, response, and evidence explicit;
- separates components through documented contracts so they can be replaced or scaled independently;
- supports a small single-node proof of concept and explains how the same boundaries can scale horizontally;
- records operational evidence, limitations, failure modes, and rollback behavior.

## Architectural principles

1. **Open-source first** — favor components that can be inspected, documented, and self-hosted.
2. **Hybrid analytics** — combine rules, enrichment, data analysis, and ML only where data and evidence support them.
3. **Modularity** — separate ingestion, storage, analytics, detection, case management, and response.
4. **Scalability** — design a clear path from Synapse Mini to a distributed deployment.
5. **Observability** — measure data flow, latency, errors, resource use, and component health.
6. **Governance and safety** — keep permissions, evidence, approval boundaries, and rollback explicit.

## Documented component set

The current material discusses components such as:

- Wazuh for SIEM/XDR telemetry and rule-based detection;
- Kafka or equivalent messaging for decoupled data flow;
- OpenSearch for indexing, search, and dashboards;
- Spark/ML or other data-analysis paths where justified;
- TheHive/Cortex for case management and enrichment;
- Docker for reproducible deployment;
- Prometheus, Grafana, OpenTelemetry, and Jaeger for observability.

A component appearing in a diagram does not prove that every integration works end to end. Operational claims require a reproducible test and retained evidence.

## Repository role

This repository is the public source for the graduation project's scope, architecture, maturity, and evidence gates.

| Concern | Canonical location |
|---|---|
| Public architecture, data flow, decisions, and roadmap | This repository |
| Runtime/POC for ingestion, triage, HITL, and evidence capture | `Project-Synapse-SOC-Factory` — private during Git-history review |
| Commercial cybersecurity service direction | [SOCRoot](https://socroot.com) — a separate project |
| SOCRoot public website | [kyriesoc](https://github.com/Muath-Yousef/kyriesoc) |

## Graduation-project completion criteria

- an updated architecture diagram with explicit boundaries and contracts;
- a component inventory with role, rationale, and alternatives;
- a documented data path from ingestion through analysis, detection, and case handling;
- at least one end-to-end integration test with an input, expected output, and acceptance criteria;
- baseline measurements for latency, data volume, resource consumption, and failures;
- a documented path from a constrained POC to a distributed deployment;
- a delivery package covering setup, verification, limitations, and rollback.

## Safety invariants

1. `SOAR_DRY_RUN=true` by default.
2. Sensitive actions require human approval.
3. CDN and RFC1918 addresses are never automatically blocked.
4. DNS events produce `NOTIFY_ONLY`, never `BLOCK_IP`.
5. Raw client data is never sent to external AI providers.
6. Every action must produce traceable evidence and support rollback.

## Maturity

**Status: active graduation-project architecture and prototype validation.**

The project does not claim full end-to-end production readiness, a proven SLA, autonomous remediation, sovereign or national-grade capability, or performance figures that are not backed by reviewable tests.

## Relationship with SOCRoot

[SOCRoot](https://socroot.com) is a separate commercial innovation focused on subscription-based, automatable cybersecurity services with measurable customer value.

Project Synapse and SOCRoot may reuse patterns or components, but:

- technical evidence from Project Synapse does not prove that a customer will pay for SOCRoot;
- a SOCRoot subscription does not by itself validate the Project Synapse academic deliverable;
- shared code does not merge their scope, ownership, or success criteria.

## Documentation

- [Overview](docs/overview.md)
- [Architecture](docs/architecture.md)
- [Roadmap](docs/roadmap.md)
