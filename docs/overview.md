# Project Synapse Overview

## Academic identity

Project Synapse is Mu'ath Yousef's 2025–2026 graduation project at Tafila Technical University. Its academic deliverable is titled **“Project Synapse: AI-Driven Hybrid SOC Platform — From Enterprise Vision to Proof-of-Concept Implementation.”**

The project investigates whether an open-source, stream-processing architecture can provide explainable, scalable security detection while reducing dependence on expensive, opaque commercial SIEM platforms.

## Contribution model

Project Synapse has three related but separately evaluated contributions.

### 1. Enterprise architecture

A six-layer design covering:

1. data collection;
2. durable event streaming;
3. rule-based and behavioral detection;
4. searchable evidence storage;
5. case management and SOAR;
6. observability and secrets management.

The design target is a distributed, multi-datacenter deployment. It is an architecture and capacity model, not evidence that a 90-node system is currently deployed.

### 2. PSM proof of concept

PSM (Proactive Security Monitoring) is a deliberately constrained, single-node implementation. It validates the most important architectural assumption: security events can move through Kafka, Spark detection, Kafka alerts, Logstash, and OpenSearch with measurable behavior.

PSM removes high availability, replication, geographic distribution, and broad threat coverage. Its role is experimental validation, not production equivalence.

### 3. Controlled CVE lab workflow

The graduation-development plan also defines Synapse Arm / CLI for authorized lab work:

- initialize a CVE environment;
- reproduce exploitation under controlled conditions;
- observe detection;
- apply a patch or mitigation;
- verify the exploit no longer succeeds;
- preserve evidence and generate a report.

This is a planned graduation workflow whose implementation evidence must be tracked separately from the PSM benchmark.

## Research question

> Can a hybrid open-source SOC architecture combine explainable rules and stateful stream analytics, prove its core design on constrained infrastructure, and retain a credible path toward horizontal scale?

## Hybrid detection

The architecture combines:

- **signature and rule-based detection** using Wazuh and Sigma for explainable known patterns;
- **behavioral detection** using Spark Structured Streaming for windows, aggregation, sequences, and contextual enrichment;
- **future ML integration** only after appropriate data, labels, baselines, and feedback loops exist.

The current PSM report documents two privilege-escalation rules:

- `SUDO_SHELL_EXECUTION` — matches suspicious sudo shell execution;
- `SUDO_ABUSE_SPIKE` — detects five or more sudo events within a stateful time window.

## Reported PSM results

The academic report records:

- 60,000 events processed in 62 seconds;
- 967 events/second sustained and 1,200 events/second peak;
- 15.96-second average latency, 17.8-second P95, and 18.2-second P99;
- 95.9% precision, 94.0% recall, and 94.9% F1 on 100 labeled cases;
- 2,847,391 events in a seven-day simulation with 1,247 alerts.

These are source-backed results from the academic deliverable. They are not yet a public, independently rerunnable benchmark. The [evidence register](evidence-register.md) records that distinction.

## Scope boundaries

### Demonstrated or reported

- Kafka → Spark → Kafka → Logstash → OpenSearch POC path;
- stateful privilege-escalation detection;
- controlled accuracy and throughput measurements;
- architecture and capacity-planning model;
- Docker Compose proof-of-concept approach.

### Designed or planned

- enterprise-scale 50,000–200,000 events/second;
- multi-node and multi-datacenter deployment;
- TheHive/Cortex/Shuffle SOAR integration;
- expanded detection rules;
- ML models and analyst-feedback loops;
- complete Synapse Arm / CLI CVE lifecycle.

### Explicitly not claimed

- live production-scale deployment;
- guaranteed SLA or certification;
- complete autonomous response;
- broad threat coverage from two POC rules;
- commercial validation for SOCRoot.

## Success criteria

The graduation project is strong when a reviewer can:

1. understand the problem and design trade-offs;
2. trace data and decisions across components;
3. reproduce at least one POC scenario from sanitized inputs;
4. inspect accuracy and performance methodology;
5. distinguish measured POC results from enterprise targets;
6. review limitations, safety controls, and future work.

## Source hierarchy

Internally, the current source hierarchy is:

1. White Paper v2.0 — concept and enterprise architecture;
2. the 2025–2026 academic report — graduation delivery, methods, results, cost model, and appendices;
3. development plans — dashboard, backend, Synapse CLI, POC packaging, and future work;
4. GitHub — public, sanitized, reviewable documentation and code.

Original source files remain in Google Drive; GitHub publishes only the safe engineering narrative and evidence boundary.
