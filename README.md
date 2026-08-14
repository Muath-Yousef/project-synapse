# Project Synapse

**Project Synapse is the public architecture and documentation foundation behind SOCRoot.**

It began as a graduation project exploring how smaller organizations could access practical SOC capabilities without the cost and complexity of a traditional enterprise SOC. The work has since evolved into SOCRoot, while this repository remains the public source for architecture, scope, maturity, and engineering decisions.

## Problem statement

Small and medium-sized organizations often need monitoring, detection, incident handling, and security reporting, but cannot operate a full enterprise SOC. Project Synapse documents a modular path toward those capabilities while keeping safety, cost, privacy, and operational realism as first-class constraints.

## Repository role

This repository contains **architecture and documentation**, not the canonical runtime implementation.

| Concern | Canonical repository |
|---|---|
| Public architecture and roadmap | This repository |
| Control plane, portals, RBAC, and evidence workflows | [ide-agentic-engine](https://github.com/Muath-Yousef/ide-agentic-engine) |
| Alert ingestion, triage, orchestration, and runtime actions | [Project-Synapse-SOC-Factory](https://github.com/Muath-Yousef/Project-Synapse-SOC-Factory) |
| Product website | [kyriesoc](https://github.com/Muath-Yousef/kyriesoc) |

## Architectural scope

The target architecture brings together:

- SIEM/XDR monitoring with Wazuh
- SOAR workflows with Shuffle
- Case management with TheHive
- Evidence capture and security reporting
- Python and Docker-based services
- PostgreSQL, Redis, and OpenSearch
- Prometheus, Grafana, OpenTelemetry, and Jaeger
- AI-assisted analysis with privacy and safety boundaries
- Compliance-oriented knowledge for Jordan and UAE use cases

## Safety invariants

These rules are architectural requirements:

1. SOAR_DRY_RUN=true by default.
2. Sensitive actions require human approval.
3. CDN and RFC1918 addresses are never automatically blocked.
4. DNS events produce NOTIFY_ONLY, never BLOCK_IP.
5. Raw client data is never sent to external AI providers.
6. Every action must produce traceable evidence and support rollback.

## Maturity

**Status: active architecture and pre-production validation.**

The project demonstrates substantial engineering work, but it does not claim complete end-to-end production readiness, a proven SLA, or fully autonomous remediation. Each capability should be treated as verified only when backed by tests, deployment evidence, and a documented rollback path.

## Documentation

- [Overview](docs/overview.md)
- [Architecture](docs/architecture.md)
- [Roadmap](docs/roadmap.md)

## Intended outcome

The near-term goal is not to add more architectural layers. It is to validate one narrow, safe, commercially useful workflow for an SMB, measure delivery cost and operational risk, and turn the result into a repeatable service.
