# Phase 6 — Product Metrics & Telemetry Framework

This directory contains the measurement philosophy, North Star Metric specification, 5-level metric hierarchy, telemetry event taxonomy, conversion funnels, and experimental metric plans for **AI Career Copilot**.

---

## 1. Objectives of Phase 6

* **Define True Value Over Vanity**: Establish measurement systems that track candidate decision confidence and time allocation rather than superficial application spam or raw token usage.
* **Operationalize North Star Metric**: Provide unambiguous mathematical definitions for high-confidence career decisions.
* **Implement AI Grounding & Trust Metrics**: Create telemetry signals that independently evaluate LLM extraction accuracy, hallucination prevention, and user auditability.
* **Design Future Experimentation Framework**: Outline structured A/B testing plans to validate core product hypotheses in future releases.

---

## 2. North Star Metric: Weekly High-Confidence Career Decisions (W-HCCD)

> **"The number of unique job opportunities where a candidate has reviewed the explainable qualification breakdown and executed a deliberate, committed triage action (Prioritized, Saved with Notes, or Discarded) within a 7-day window."**

$$\text{W-HCCD} = \sum \text{Deliberate Triage Actions following Qualified Review per Active Candidate per Week}$$

---

## 3. Metrics Artifact Directory

| Document | Core Contribution |
| :--- | :--- |
| [`metrics-framework.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/metrics-framework.md) | Measurement philosophy, 5-level metric hierarchy, 9 functional dimensions, 5 guardrail metrics, and metric anti-patterns. |
| [`north-star-metric.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/north-star-metric.md) | Formal operational definition of W-HCCD, decomposition into 3 input drivers, alternative rejections, and structural limitations. |
| [`metric-definitions.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/metric-definitions.md) | Exhaustive metric dictionary covering Activation, Efficiency, Quality, Trust, Prioritization, Tracking, Retention, AI Quality, and Reliability with traceability mappings. |
| [`event-taxonomy.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/event-taxonomy.md) | Structured event schema (triggers, properties, sampling strategy) and strict PII privacy boundaries. |
| [`funnel-analysis.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/funnel-analysis.md) | 10-stage core product funnel (Profile ➔ Ingest ➔ Review ➔ Decide ➔ Track), drop-off diagnostics, and corrective product actions. |
| [`experiment-metrics.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/experiment-metrics.md) | 4 candidate A/B experiment plans (Qualitative Tiers vs. Scores, Evidence-First UI, Raw Paste vs. URL, Auto-Queue vs. Agency) with decision rules. |
| [`metrics-decision-log.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/metrics-decision-log.md) | 6 interview-defensible telemetry decision records detailing rationales, alternatives, consequences, and revisit triggers. |

---

## 4. Metric Hierarchy Summary

```
┌────────────────────────────────────────────────────────────────────────┐
│ 1. NORTH STAR METRIC:                                                  │
│    Weekly High-Confidence Career Decisions (W-HCCD)                    │
├────────────────────────────────────────────────────────────────────────┤
│ 2. PRIMARY OUTCOME METRICS:                                            │
│    • Median Time-to-Decision (<90s) • High-Fit Acceptance Rate (HFAR)  │
│    • Queue Execution Rate (QER)     • Interview Context Retrieval Rate │
├────────────────────────────────────────────────────────────────────────┤
│ 3. PRODUCT HEALTH METRICS:                                             │
│    • Profile Activation Rate (PAR)  • Weekly Active Decision-Makers    │
│    • Snapshot Persistence Rate      • 3-Week Cohort Retention          │
├────────────────────────────────────────────────────────────────────────┤
│ 4. DIAGNOSTIC METRICS:                                                 │
│    • Ingestion Mode Ratio (Paste/URL) • Evidence Inspection Rate (EIR) │
│    • Gap Severity Distribution      • Manual Priority Override Rate    │
├────────────────────────────────────────────────────────────────────────┤
│ 5. GUARDRAIL METRICS:                                                  │
│    • Unsupported Evidence Rate (<1%)• Zero-Second Triage Rate (<35%)   │
│    • High-Fit Override Rate (<25%)  • System Ingestion Error Rate (<1%)│
└────────────────────────────────────────────────────────────────────────┘
```
