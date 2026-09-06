# Phase 7 — Product Experimentation & Validation Framework

This directory contains the formal experimentation framework, hypothesis backlog, detailed experiment designs, 5-stage validation roadmap, decision rules, and research decision logs for **AI Career Copilot**.

---

## 1. Objectives of Phase 7

* **Scientific De-Risking**: Establish rigorous experimental protocols to validate critical product hypotheses before committing production engineering resources.
* **Falsifiable Product Hypotheses**: Transition from strategic assumptions to measurable, testable predictions.
* **Dual-Track AI Validation**: Independently monitor LLM grounding and extraction fidelity alongside user behavioral metrics.
* **End-to-End Value Proof**: Benchmark the integrated AI Career Copilot decision loop against the status quo stack (LinkedIn + ChatGPT + Google Sheets).

---

## 2. Experimentation Philosophy: Decisions Over Cosmetics

```
┌────────────────────────────────────────────────────────────────────────┐
│                   EXPERIMENTATION INTEGRITY PRINCIPLES                 │
├────────────────────────────────────────────────────────────────────────┤
│ • Test Core Decision Bottlenecks, Not Button Colors.                   │
│ • Model Safety & Grounding (<1% Hallucinations) is a Hard Launch Gate. │
│ • Multi-Stage Uncertainty Reduction: Discovery ➔ Prototype ➔ Pilot.    │
│ • Value Both Outcomes: Deciding NOT to apply is a valid success.       │
│ • Zero Fabricated Traction: All tests clearly tagged as [HYPOTHESIS].  │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Experimentation Artifact Directory

| Document | Core Contribution |
| :--- | :--- |
| [`experimentation-framework.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/07-Experimentation/experimentation-framework.md) | Epistemological standards, 6-stage progressive uncertainty reduction model, dual-track AI validation, and experimentation anti-patterns. |
| [`hypothesis-backlog.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/07-Experimentation/hypothesis-backlog.md) | Consolidated backlog of 10 falsifiable hypotheses categorized by risk, uncertainty, validation method, and priority tier (P0/P1/P2). |
| [`experiment-designs.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/07-Experimentation/experiment-designs.md) | Protocols for 5 core experiments (Qualitative Tiers vs. Scores, Evidence-First UI, Raw Paste vs. URL, 3-Tier Queue, and End-to-End Benchmark). |
| [`validation-plan.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/07-Experimentation/validation-plan.md) | 5-stage validation roadmap (Problem, Prototype, Workflow Benchmark, Cohort Pilot, Controlled A/B Tests) with exit criteria. |
| [`decision-rules.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/07-Experimentation/decision-rules.md) | Post-experiment decision taxonomy (Positive, Mixed, Neutral, Negative, Kill-Switch) and end-to-end traceability matrix. |
| [`experimentation-decision-log.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/07-Experimentation/experimentation-decision-log.md) | 6 research decision records detailing rationales, alternatives, consequences, and revisit triggers. |

---

## 4. Core Experiments Summary

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CORE EXPERIMENT PROTOCOLS                       │
├────────────────────────────────────────────────────────────────────────┤
│ EXP-01: Qualitative Tiers vs. Numerical Scores (P0 Launch Gate)        │
│ • Hypothesis: Qualitative tiers produce higher decision conviction.    │
│ • Primary Metric: Decision Conviction Rate (DCR).                      │
├────────────────────────────────────────────────────────────────────────┤
│ EXP-02: Evidence-First vs. Summary-First UI (P0 Launch Gate)           │
│ • Hypothesis: Grounded resume citations eliminate AI skepticism.       │
│ • Primary Metric: Evidence Inspection Rate (EIR).                      │
├────────────────────────────────────────────────────────────────────────┤
│ EXP-03: Raw Text Ingestion vs. URL Scraping (P1 Ingestion Test)        │
│ • Hypothesis: 1-click text paste eliminates login-wall drop-off.       │
│ • Primary Metric: First Ingestion Completion Rate (FICR).              │
├────────────────────────────────────────────────────────────────────────┤
│ EXP-04: System 3-Tier Queue vs. Manual Flat List (P1 Queue Test)       │
│ • Hypothesis: Automated triage drives higher 7-day application sprints.│
│ • Primary Metric: 7-Day Queue Execution Rate (QER).                    │
├────────────────────────────────────────────────────────────────────────┤
│ EXP-05: Core End-to-End Product Value Benchmark (P0 Value Proof)       │
│ • Hypothesis: Copilot cuts evaluation time >50% & improves accuracy.   │
│ • Primary Metric: Evaluation Velocity & Blocker Detection Accuracy.    │
└────────────────────────────────────────────────────────────────────────┘
```
