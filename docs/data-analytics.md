# Data Analytics and Evaluation

## Purpose

Data analytics is a measured Project Synapse workstream. It covers both security-detection quality and pipeline performance. Each result must connect a defined input, method, metric, and limitation.

## Current PSM evaluation

### Detection logic

The academic report evaluates two privilege-escalation patterns:

| Rule | Method | Expected behavior |
|---|---|---|
| `SUDO_SHELL_EXECUTION` | string/rule filtering for `sudo` plus shell execution | generate a HIGH alert |
| `SUDO_ABUSE_SPIKE` | stateful aggregation over a time window | generate a CRITICAL spike alert |

Documented negative testing included 100 benign SSH and file-operation entries with no sudo pattern; the report records zero alerts for that test.

### Labeled-case metrics

The report records a 100-case confusion matrix:

| Outcome | Count |
|---|---:|
| True positives | 47 |
| False positives | 2 |
| False negatives | 3 |
| True negatives | 48 |

Derived results:

- precision: **95.9%**;
- recall: **94.0%**;
- F1: **94.9%**;
- accuracy: **95.0%**.

Known false-positive contexts include legitimate administrator troubleshooting and configuration-management activity. Known false-negative examples include alternate shells, slow-paced attacks, and obfuscated commands. These limitations matter more than a single headline score.

### Pipeline performance

| Metric | Reported value |
|---|---:|
| 60,000-event sustained rate | 967 events/second |
| five-second peak | 1,200 events/second |
| consumer lag | 0 messages |
| Spark CPU | 48% peak; 35% average |
| OpenSearch indexing | 950 documents/second |
| average latency | 15.96 seconds |
| P95 latency | 17.8 seconds |
| P99 latency | 18.2 seconds |
| maximum latency | 19.4 seconds |

The report also records a seven-day simulation of 2,847,391 events and 1,247 generated alerts. These are report-backed POC results; public raw fixtures, scripts, and machine-readable outputs are still required for independent reproduction.

## Reproducibility contract

A public benchmark package should include:

1. sanitized generator and seed;
2. event schema and exact count;
3. hardware/VM specification;
4. component images and versions;
5. Kafka/Spark/OpenSearch configuration;
6. detection-rule version;
7. warm-up and measurement window;
8. latency timestamp definition;
9. confusion-matrix labeling procedure;
10. raw result file and calculation notebook/query.

Without these artifacts, the figures are useful academic evidence but not an independently verified public benchmark.

## Enterprise targets are not measurements

The enterprise documents discuss 50,000–200,000 events/second across a distributed design. That range is a capacity-planning target. It must not be combined with PSM's measured results or described as achieved.

Likewise, projected operating cost and savings are model outputs dependent on endpoint count, ingestion, retention, infrastructure pricing, staffing, and comparison assumptions. They should be published with a reproducible cost model before being treated as validated economic results.

## Future analytics path

1. expand descriptive analysis across sources, severities, and latency;
2. add 10–15 versioned rules for lateral movement, persistence, and credential access;
3. establish reviewer-labeled datasets and inter-rater guidance;
4. compare rules against a simple statistical baseline;
5. evaluate Isolation Forest or another explainable anomaly baseline;
6. add feedback, drift, and threshold monitoring only after labels are credible;
7. keep human review responsible for findings and response.

## Minimum dataset contract

Every analysis records:

- source, authorization, and version;
- time window, sample, and exclusions;
- field definitions and transformations;
- missingness, duplicates, outliers, and label quality;
- model/rule version and threshold;
- result, uncertainty, and operational interpretation;
- retention, sanitization, and deletion expectations.

Raw client or production data is not a public portfolio artifact and is not sent to external AI providers.
