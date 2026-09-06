# Product Hypothesis Backlog

This document consolidates all critical assumptions, product hypotheses, and validation requirements identified across Phases 1 through 6 of **AI Career Copilot**, prioritized by decision risk and learning cost.

---

## 1. Consolidated Hypothesis Backlog Table

| ID | Falsifiable Hypothesis Statement | Source Phase | Impact If Wrong | Uncertainty Level | Proposed Validation Method | Measurable Success Signal | Priority Tier |
| :--- | :--- | :---: | :---: | :---: | :--- | :--- | :---: |
| **HYP-01** | Early-career candidates find **qualitative fit tiers** (*Strong/Stretch/Low*) more actionable and trustworthy than a single numerical percentage match score `[HYPOTHESIS]`. | Phase 2 / Phase 4 | **Critical** | High | Prototype Testing & A/B Experiment (`EXP-01`) | Higher Decision Conviction Rate (DCR); lower hesitation time `[DESIGN TARGET]`. | **P0 (Pre-Commit)** |
| **HYP-02** | Displaying **grounded evidence citations** linking directly to candidate resume bullets eliminates AI hallucination skepticism `[HYPOTHESIS]`. | Phase 3 / Phase 4 | **Critical** | Medium | Usability Testing & A/B Experiment (`EXP-02`) | Evidence Inspection Rate >40%; <1% user-reported false claims `[DESIGN TARGET]`. | **P0 (Pre-Commit)** |
| **HYP-03** | Decomposing job requirements into **Core Prerequisites vs. Preferred Tools** reduces candidate evaluation time from 30+ minutes to <90 seconds `[HYPOTHESIS]`. | Phase 1 / Phase 3 | **High** | Medium | Timed Usability Benchmark (`EXP-05`) | Median Time-to-Decision <90s across 10 sample technical JDs `[DESIGN TARGET]`. | **P0 (Pre-Commit)** |
| **HYP-04** | Offering **1-click raw JD text pasting** as primary ingestion guarantees 100% onboarding reliability compared to fragile URL scrapers `[HYPOTHESIS]`. | Phase 5 | **High** | Low | Controlled Ingestion Test (`EXP-03`) | Ingestion completion rate >95% vs <75% for URL scraping `[DESIGN TARGET]`. | **P0 (Pre-Commit)** |
| **HYP-05** | Segmenting missing skills into **Blocking vs. Learnable Gaps** prevents candidate self-disqualification on viable stretch roles `[HYPOTHESIS]`. | Phase 1 / Phase 3 | **High** | High | Prototype Task Testing | Stretch role acceptance rate increases by >25% without fatal errors `[DESIGN TARGET]`. | **P1 (Pilot Stage)** |
| **HYP-06** | Preserving **immutable local JD snapshots** eliminates interview anxiety and context loss when live external job postings expire `[HYPOTHESIS]`. | Phase 3 / Phase 4 | **High** | Medium | Pilot Cohort Telemetry | >60% of candidates in screening stages access the Interview Drawer `[DESIGN TARGET]`. | **P1 (Pilot Stage)** |
| **HYP-07** | A **3-tier opportunity queue** reduces decision paralysis and drives focused 5–10 application sprints each week `[HYPOTHESIS]`. | Phase 1 / Phase 5 | **Medium** | Medium | A/B Testing (`EXP-04`) | 7-day Tier 1 Queue Execution Rate >50% `[DESIGN TARGET]`. | **P1 (Pilot Stage)** |
| **HYP-08** | Final-year students will maintain an **integrated Kanban tracker** if updating status requires only 1-click drag-and-drop `[HYPOTHESIS]`. | Phase 3 / Phase 5 | **Medium** | High | 3-Week Cohort Pilot | >45% weekly status update retention throughout active search `[DESIGN TARGET]`. | **P1 (Pilot Stage)** |
| **HYP-09** | Displaying **prominent ambiguity alerts** on low-signal JDs prevents candidate false confidence in vague postings `[HYPOTHESIS]`. | Phase 4 / Phase 6 | **Medium** | Low | User Audit Feedback | >70% of candidates audit raw text when ambiguity warning is triggered `[DESIGN TARGET]`. | **P2 (Post-MVP)** |
| **HYP-10** | Enabling candidates to link **live GitHub repository URLs** increases fit scoring accuracy for non-traditional candidates `[HYPOTHESIS]`. | Phase 3 / Phase 5 | **Low** | High | Quantitative Pilot Sample | Increased match precision on candidates with non-CS STEM degrees `[DESIGN TARGET]`. | **P2 (Post-MVP)** |

---

## 2. Prioritization Logic for the Hypothesis Backlog

```
┌────────────────────────────────────────────────────────────────────────┐
│                    HYPOTHESIS RISK & LEARNING MATRIX                   │
├────────────────────────────────────────────────────────────────────────┤
│ HIGH IMPACT / HIGH UNCERTAINTY (P0 — Must Validate Immediately):       │
│ • HYP-01 (Qualitative Tiers vs. Numerical Scores)                      │
│ • HYP-02 (Evidence Citations & Trust)                                  │
│ • HYP-03 (Time-to-Decision Reduction)                                  │
│ • HYP-04 (Raw Text Ingestion Reliability)                              │
├────────────────────────────────────────────────────────────────────────┤
│ HIGH IMPACT / MEDIUM UNCERTAINTY (P1 — Validate in Pilot):             │
│ • HYP-05 (Gap Severity Differentiation)                                │
│ • HYP-06 (Snapshot Context Retention)                                  │
│ • HYP-07 (3-Tier Queue Triage)                                         │
│ • HYP-08 (Kanban Tracking Habit Retention)                             │
├────────────────────────────────────────────────────────────────────────┤
│ MODERATE IMPACT / LOW RISK (P2 — Validate in Later Releases):          │
│ • HYP-09 (Ambiguity Alert Heed Rate)                                   │
│ • HYP-10 (GitHub Deep Linking Accuracy)                                │
└────────────────────────────────────────────────────────────────────────┘
```
