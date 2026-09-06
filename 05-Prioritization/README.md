# Phase 5 — Product Prioritization & Trade-Offs

This directory contains the formal prioritization framework, scored feature backlog, trade-off analyses, topological dependency maps, and strategic decision logs for **AI Career Copilot**.

---

## 1. Objectives of Phase 5

* **Establish Objective Prioritization**: Replace intuition with a defensible, dependency-aware framework adapted for early-stage AI decision products.
* **Define Strict MVP Scope Boundaries**: Articulate exactly what must be built in the initial release, what should follow in rapid iterations, and what must be explicitly rejected.
* **Document Strategic Sacrifices**: Clearly record the trade-offs made and capabilities intentionally given up to ensure sharp execution focus.

---

## 2. Selected Framework: Dependency-Aware Value-Risk Framework (DAVR)

We evaluate all backlog capabilities across four dimensions:
1. **User Impact** (1 to 5): Direct reduction of cognitive evaluation friction.
2. **JTBD Alignment** (1.0 to 1.5 Multiplier): Direct fulfillment of the primary decision job.
3. **Confidence Level** (0.5 to 1.0 Factor): Grounded empirical evidence vs. unvalidated hypothesis.
4. **Relative Effort & Risk** (1 to 5): Technical complexity and AI uncertainty.

$$\text{DAVR Priority Score} = \frac{\text{User Impact} \times \text{JTBD Multiplier} \times \text{Confidence}}{\text{Relative Effort}}$$

---

## 3. Prioritization Artifact Directory

| Document | Core Contribution |
| :--- | :--- |
| [`prioritization-framework.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/prioritization-framework.md) | Framework comparison, DAVR scoring methodology, qualitative proxy scales, and 6 governing prioritization principles. |
| [`feature-backlog.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/feature-backlog.md) | Scored backlog of 22 capabilities, constrained MVP scenario (P0/P1/P2/P3), and the "If We Could Only Build 3 Things" extreme MVP analysis. |
| [`trade-off-analysis.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/trade-off-analysis.md) | Deep analysis of 6 strategic trade-offs (Depth vs. Breadth, Agency vs. Automation, Scores vs. Tiers) and explicit documentation of what was sacrificed. |
| [`dependency-map.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/dependency-map.md) | Topological dependency architecture, hard blockers, soft enhancers, and critical path release sequencing. |
| [`prioritization-decision-log.md`](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/prioritization-decision-log.md) | 6 interview-defensible decision records with context, alternatives, rationales, consequences, and revisit triggers. |

---

## 4. MVP Prioritization Summary

```
┌────────────────────────────────────────────────────────────────────────┐
│                        MVP PRIORITIZATION TIERS                        │
├────────────────────────────────────────────────────────────────────────┤
│ P0 — CORE MVP (Must Build):                                            │
│ • FB-CP-01/02: Resume PDF Parsing & Manual Skill/Project Verification  │
│ • FB-JD-01: Raw JD Text Ingestion (100% Reliable Input)                │
│ • FB-PS-01: Requirement Structuring (Hard vs. Preferred Criteria)      │
│ • FB-FA-01/02/03/04: Explainable Fit Engine + Evidence + Gap Severity   │
│ • FB-PR-01: 3-Tier Opportunity Triage Queue                            │
│ • FB-TR-01/02: Immutable Snapshot Archival & 7-Stage Kanban Tracker    │
├────────────────────────────────────────────────────────────────────────┤
│ P1 — IMPORTANT ENABLERS (Should Build):                                │
│ • FB-JD-02: Live URL Ingestion with Fallback                           │
│ • FB-PS-02: Low-Signal / Ambiguity Warning Alerts                      │
│ • FB-TR-03: Slide-Out Interview Preparation Context Drawer             │
│ • FB-FA-05: Actionable Narrative Recommendations                       │
│ • FB-CP-03: Target Role & Workplace Preferences                        │
│ • FB-PR-02: Manual Priority Override & Drag-and-Drop Triage            │
├────────────────────────────────────────────────────────────────────────┤
│ P2 — DEFER TO POST-MVP (Later):                                        │
│ • FB-CP-04: GitHub Live Project URL Scraping                           │
│ • FB-PR-03: Advanced Role Filtering & Urgency Sorting                  │
│ • FB-TR-04: Funnel Drop-off & Rejection Stage Logging                  │
├────────────────────────────────────────────────────────────────────────┤
│ P3 — EXPLICIT NON-GOALS (Won't Build / Reject):                        │
│ • FB-NO-01: Automated ATS Application Submission Bots (Spam prevention)│
│ • FB-NO-02: Generic Resume Hallucination Generator                     │
└────────────────────────────────────────────────────────────────────────┘
```
