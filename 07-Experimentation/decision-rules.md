# Experiment Decision Rules & Traceability Matrix

This document defines the post-experiment decision taxonomy, pre-commit threshold standards, safety kill-switches, and end-to-end traceability matrix for **AI Career Copilot**.

---

## 1. Post-Experiment Outcome Taxonomy

To eliminate subjective post-hoc rationalization, all experiment outcomes are categorized into five structured decision paths:

```
┌────────────────────────────────────────────────────────────────────────┐
│                     POST-EXPERIMENT DECISION PATHS                     │
├────────────────────────────────────────────────────────────────────────┤
│ 1. STRONGLY POSITIVE   ➔ Statistically significant win; scale variant. │
│ 2. MIXED RESULTS       ➔ Primary metric up, secondary down; iterate.   │
│ 3. NEUTRAL / FLAT      ➔ No statistical lift; analyze qualitative logs.│
│ 4. NEGATIVE OUTCOME    ➔ Primary metric down; rollback immediately.    │
│ 5. SAFETY/TRUST BREACH ➔ Guardrail failed; instant kill-switch abort.  │
└────────────────────────────────────────────────────────────────────────┘
```

| Outcome Category | Operational Definition | Mandatory Product Action |
| :--- | :--- | :--- |
| **1. Strongly Positive** | Primary metric demonstrates statistically significant improvement ($p < 0.05$) AND all guardrail metrics remain within safe thresholds. | **Scale & Roll Out**: Promote treatment variant to 100% production traffic. Document learning in PRD. |
| **2. Mixed Results** | Primary metric improves, but a key secondary metric declines (e.g., decision conviction rises but time-to-decision increases by 40%). | **Iterate & Retest**: Refine UI friction points to isolate the root cause and launch a follow-up test. |
| **3. Neutral / Flat** | No statistically significant difference between control and treatment variants. | **Qualitative Deep-Dive**: Conduct 5 user interviews to understand why the intervention produced zero behavioral shift. |
| **4. Negative Outcome** | Primary metric degrades or user drop-off increases with statistical significance. | **Rollback & Discard**: Revert immediately to control. Catalog falsified hypothesis in decision log. |
| **5. Safety / Trust Breach** | Any AI guardrail fails (e.g. Unsupported Evidence Rate $>1.0\%$ or Hallucination Rate $>2.0\%$), regardless of primary conversion wins. | **Instant Kill-Switch**: Terminate experiment immediately. Model quality/trust always trumps vanity conversion `[PRODUCT INFERENCE]`. |

---

## 2. Pre-Commit Decision Rule Standards

> **Rule of Experimental Integrity**: All hypothesis evaluation thresholds, sample sizes, and guardrail limits must be formally documented **prior to launching traffic allocation** `[FACT]`.

* Where exact production sample sizes are currently uncalibrated, they are labeled as `[VALIDATION REQUIRED]` and must be calculated via power analysis prior to live testing.

---

## 3. End-to-End Product Traceability Matrix

This matrix establishes the unbroken logical chain from Phase 1 problem discovery through to Phase 7 experimentation:

| Phase 1 Problem | Related JTBD | Phase 5 Prioritization Decision | Phase 6 Metric Monitored | Phase 7 Experiment Protocol | Core Product Learning Needed |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **`PP-05` Opaque Match Badges** | `JTBD 1` | `PD-06` Adopt Qualitative Tiers over Scores | `M-DEC-01` High-Fit Acceptance Rate | **`EXP-01`** (Qualitative Tiers vs. % Scores) | Do qualitative tiers provide higher decision conviction than numerical scores? `[HYPOTHESIS]` |
| **`PP-05` AI Skepticism** | `JTBD 1` | `PD-03` Prioritize Grounded Evidence Citations | `M-TRS-01` Evidence Inspection Rate | **`EXP-02`** (Evidence-First UI Architecture) | Does surfacing resume project citations eliminate AI hallucination doubts? `[HYPOTHESIS]` |
| **`PP-01` Board Fragmentation**| `JTBD 1` | `PD-02` Prioritize 100% Reliable Raw Text Paste | `M-ACT-02` First Job Ingestion Rate | **`EXP-03`** (Raw Text vs. URL Ingestion) | Does raw text pasting prevent onboarding drop-off caused by login-walled URLs? `[HYPOTHESIS]` |
| **`PP-07` Tab Triage Paralysis**| `JTBD 2` | `PD-01` Build 3-Tier Prioritization Queue | `M-PRI-01` 7-Day Queue Execution Rate | **`EXP-04`** (3-Tier Queue vs. Flat List) | Does automatic priority tiering reduce decision time and drive focused application sprints? `[HYPOTHESIS]` |
| **`PP-03` Bloated JDs & Noise** | `JTBD 1` | `PD-01` Focus on Core Decision Loop | `M-EFF-01` Median Time-to-Decision | **`EXP-05`** (Core Value Loop vs. Status Quo) | Does AI Career Copilot cut evaluation time by $>50\%$ while improving blocker accuracy? `[HYPOTHESIS]` |
| **`PP-09` Expired 404 Links** | `JTBD 5` | `PD-04` Include Immutable Snapshot Archival | `M-TRK-02` Interview Context Retrieval Rate | **Stage 4 Pilot** (Cohort Context Retention) | Does local snapshot retention eliminate interview context loss when postings close? `[HYPOTHESIS]` |
