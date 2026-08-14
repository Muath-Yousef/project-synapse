# Data Analytics Method

## Purpose

Data analytics is a core Project Synapse workstream, not a decorative dashboard layer. Each analysis must start with a clear security question and end with a reproducible result, uncertainty statement, and operational interpretation.

## Candidate research questions

Examples suitable for the graduation project include:

- Which event sources contribute the most alert volume and noise?
- How do rule severity and observed case priority differ?
- Which repeated patterns indicate a candidate correlation or suppression rule?
- How does ingestion-to-triage latency change with event volume?
- Can a simple statistical or ML method improve prioritization over a documented rule-based baseline?

The project should select a small number of questions that can be answered with available, authorized, and well-defined data.

## Reproducible pipeline

```mermaid
flowchart LR
    A["Authorized or synthetic source"] --> B["Schema validation"]
    B --> C["Quality checks"]
    C --> D["Versioned transformation"]
    D --> E["Exploration / baseline"]
    E --> F["Rule, statistic, or model"]
    F --> G["Evaluation"]
    G --> H["Security interpretation"]
    H --> I["Evidence artifact and limitations"]
```

## Minimum dataset contract

Every analysis artifact should record:

- dataset name and version;
- origin and authorization;
- time window and sampling method;
- field definitions and units;
- inclusion, exclusion, and sanitization rules;
- missingness, duplicates, outliers, and label quality;
- transformation code or query version;
- retention and deletion expectations.

Do not publish raw client or production data. Public examples should use synthetic or sanitized fixtures with reserved domains and addresses.

## Analysis progression

### 1. Descriptive baseline

Start with counts, rates, distributions, time patterns, source coverage, severity mix, and processing latency. This establishes whether the dataset is usable before introducing complex methods.

### 2. Data-quality assessment

Measure missing fields, invalid timestamps, duplicate events, schema drift, inconsistent labels, and source imbalance. A model result is not credible when its inputs are not understood.

### 3. Rule and correlation evaluation

Compare existing rules or correlations using documented metrics. Record what is treated as a true or false result and how uncertainty is reviewed.

### 4. Statistical or ML evaluation

Use ML only when it answers a defined question better than a simpler baseline. Keep the feature set, split strategy, leakage checks, hyperparameters, and evaluation code reviewable.

## Evaluation metrics

Metric choice depends on the question. Candidate measures include:

| Objective | Candidate measures |
|---|---|
| Alert prioritization | precision, recall, F1, false-positive rate |
| Ranking | precision@k, recall@k, mean reciprocal rank |
| Anomaly review | reviewer-confirmed hit rate, alert volume reduction |
| Pipeline performance | end-to-end latency, throughput, error rate, resource use |
| Operational usefulness | time-to-triage, duplicate reduction, evidence completeness |

Accuracy alone is rarely sufficient for imbalanced security data. Report the baseline, class distribution, threshold, and confidence interval or uncertainty where practical.

## Evidence artifact template

Each notebook, query, or report should contain:

1. question and decision context;
2. source and dataset contract;
3. quality checks;
4. method and baseline;
5. result with appropriate visual or table;
6. security interpretation;
7. limitations and possible bias;
8. reproducibility instructions;
9. artifact version and evidence links.

## AI and privacy boundary

- do not send raw operational data to external AI providers;
- minimize and sanitize any context used for assisted analysis;
- label AI-generated hypotheses as unverified until tested;
- retain the deterministic query, code, or rule that supports the conclusion;
- keep a human responsible for findings and response decisions.

## Completion gate

The analytics workstream is complete for graduation review when at least one security question can be reproduced from a documented synthetic or authorized dataset, compared with a baseline, evaluated with suitable metrics, and explained with limitations and operational relevance.
