# Project Synapse Evidence Register

This register separates measured PSM results, architecture targets, cost projections, and future work. The source documents remain in the owner's Google Drive; this public page contains a sanitized claim inventory and does not expose private source links.

## Source hierarchy

| Source | Role |
|---|---|
| White Paper Project Synapse v2.0 | enterprise concept, architectural principles, sovereignty, and scale model |
| Project Synapse: AI-Driven Hybrid SOC Platform — From Enterprise Vision to POC Implementation | academic delivery, PSM method, results, cost analysis, and appendices |
| Project Synapse development plan | dashboard/backend direction and Synapse Arm / CLI CVE workflow |
| Synapse Mini implementation plan | single-node resource and integration plan |
| GitHub | public, sanitized, reproducible documentation and code |

## Claim register

| Claim | Class | Current support | Public verification status |
|---|---|---|---|
| PSM uses Kafka → Spark → Kafka → Logstash → OpenSearch | POC architecture | academic report and appendices | source-backed; public setup pending |
| 60,000 events processed in 62 seconds | measured POC result | academic benchmark appendix | source-backed; raw output pending |
| sustained throughput 967 events/second | measured POC result | academic benchmark appendix | source-backed; rerun pending |
| average latency 15.96 seconds | measured POC result | academic benchmark appendix | source-backed; rerun pending |
| P95/P99 latency 17.8/18.2 seconds | measured POC result | academic benchmark appendix | source-backed; rerun pending |
| precision 95.9%, recall 94.0%, F1 94.9% | measured POC result | 100 labeled-case evaluation | source-backed; labels and script pending |
| 2,847,391-event seven-day simulation | measured POC result | academic results chapter | source-backed; raw log pending |
| 50,000–200,000 events/second | enterprise target | White Paper and capacity model | not a deployed or measured result |
| 90+ node enterprise topology | enterprise design | academic architecture | not deployed |
| $2,365/month enterprise cost | projection | academic cost model | assumptions need public model |
| 80–91% commercial-SIEM savings | projection | comparison model | not audited procurement evidence |
| Synapse Arm CVE commands | planned workflow | development plan | command-level evidence pending |
| TheHive/Cortex/Shuffle SOAR | designed/future integration | architecture and roadmap | end-to-end integration pending |
| ML anomaly detection | future work | architecture extension | no current production claim |

## PSM test detail

### Functional tests recorded

- single sudo shell execution → one HIGH alert: PASS;
- seven sudo events in five seconds → CRITICAL spike plus HIGH alerts: PASS;
- 100 benign non-sudo events → zero alerts: PASS.

### Accuracy counts recorded

- true positives: 47;
- false positives: 2;
- false negatives: 3;
- true negatives: 48.

### Known limitations

- legitimate administration and configuration-management tools may resemble malicious sudo behavior;
- alternate shells, obfuscation, and slow-paced activity may evade simple rules;
- the POC has two rules and cannot represent broad threat coverage;
- one node does not validate high availability or geographic distribution;
- report-backed evidence is weaker than a clean public reproduction package.

## Publication gate

A claim may move from **source-backed** to **publicly reproducible** only when GitHub contains or links to:

1. sanitized input or generator;
2. exact code/configuration versions;
3. execution instructions;
4. machine-readable output;
5. calculation method;
6. limitations and environment details.

Production claims require additional deployment, security, resilience, and operational evidence.
