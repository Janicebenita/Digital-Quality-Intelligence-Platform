# DQIP Quality Investigator: Explainability

## Decision and reasoning

The intended decision is which quality exception or process signal merits investigation first and which corrective-action questions a reviewer should consider. The reasoning combines DQIP's evaluated record status, specification exceptions, variation and capability measures, trends, and risk indicators with the chosen domain context. A possible cause is a hypothesis rather than a proven root cause, and any recommended measure is a proposal for human review. The repository describes quality analytics and guidance; a separately demonstrated agent execution path is needed before claiming that this agent runs independently.

## Inputs and data sources

The intended input is an operator's investigation request, a selected quality domain, and an evaluated CSV or Excel dataset with the applicable limits and mappings. DQIP accepts uploaded files or sample datasets and computes domain-aware results using its Python analytics application. Construction Quality is the repository's validated demonstration workflow; the Manufacturing, Laboratory QA, Healthcare, Pharmaceuticals, and Environmental Monitoring profiles are illustrative.

## Limits and known constraints

A central limitation is that an output depends on the quality of the uploaded measurements, selected schema, valid specifications, and appropriateness of the statistical assumptions. The illustrative domain profiles require independent validation of their rules, limits, references, and recommendations before production use. The agent must not treat a risk label or statistical association as proof of causation, assert regulatory compliance, authorize product release, or provide clinical diagnosis. Its proposed actions require review by a qualified professional against approved procedures and source records.

## Implementation in This Repository

`app.py` implements the Streamlit upload and reviewer workflow, while `analytics.py` contains the deterministic analysis. The latter maps and validates columns with `map_columns` and `validate_columns`, normalizes cube-log and SQC worksheets, prepares the data, evaluates `aci_compliance`, computes `six_sigma_metrics`, classifies risk, detects abnormalities, and builds the export report.

The application exposes the cleaned measurements, compliance flags, capability metrics, risk classification, abnormality records, and interpretation summary used in the report. Sample datasets and profiles make the construction-quality demonstration reproducible. No product-release, regulatory-approval, or corrective-action endpoint exists, so a qualified human must authorize every operational decision.

## Outputs and supporting evidence

Outputs include normalized measurement tables, specification comparisons, process metrics, triggered rules, abnormalities, risk explanations, and exportable reports. Each conclusion is linked to the uploaded values, selected limits, and named deterministic function rather than an unsupported model assertion.

## Uncertainty and human review

Schema choices, missing values, specification limits, and statistical assumptions can change the result. A qualified domain reviewer must verify the source data and approved procedures before using any recommendation.
