# Staged Product Validation Plan

This document defines the 5-stage progressive validation roadmap for **AI Career Copilot**, outlining the research methods, primary signals, participant requirements, and exit criteria for each phase.

---

## 1. Staged Validation Roadmap Overview

```
┌────────────────────────────────────────────────────────────────────────┐
│                        5-STAGE VALIDATION ROADMAP                      │
├────────────────────────────────────────────────────────────────────────┤
│ [STAGE 1: Problem Validation]   ➔ Verify real candidate friction.      │
│ [STAGE 2: Prototype Validation] ➔ Test comprehension of explainability.│
│ [STAGE 3: Workflow Validation]  ➔ Test end-to-end decision velocity.   │
│ [STAGE 4: Cohort Pilot]         ➔ Test 3-week retention & tracking.   │
│ [STAGE 5: Controlled A/B Tests] ➔ Test causal lift at scale.           │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Stage-by-Stage Validation Specifications

### Stage 1: Problem Validation (Qualitative Reality Check)
* **Core Objective**: Verify that final-year technical students genuinely suffer from decision paralysis and JD ambiguity rather than a simple lack of job listings.
* **Uncertainty Reduced**: Confirms whether the core problem framed in Phase 1 is acute enough to drive software adoption `[PRODUCT INFERENCE]`.
* **Method**: Semi-structured observational interviews where candidates screen-share an actual 30-minute job search session on LinkedIn and Handshake.
* **Participants Needed**: `[VALIDATION REQUIRED]` *(Target: 10–12 final-year CS/Data/Analytics students actively job hunting)*.
* **Primary Signal**: Candidate spends $>50\%$ of session time decoding experience checklists or opens $>20$ tabs without deciding.
* **Exit Criteria**: $\ge 80\%$ of participants explicitly express uncertainty regarding whether non-commercial project experience satisfies listed JD requirements.

---

### Stage 2: Prototype Validation (Mental Model Comprehension)
* **Core Objective**: Validate that candidates correctly interpret qualitative fit tiers (*Strong Fit*, *Stretch*, *Low Fit*), evidence citation popovers, and gap severity categories.
* **Uncertainty Reduced**: Determines whether users understand our explainable UI without confusing qualitative tiers with arbitrary percentage scores `[PRODUCT INFERENCE]`.
* **Method**: Interactive Figma wireframe walkthroughs with think-aloud protocol and comprehension task tests.
* **Participants Needed**: `[VALIDATION REQUIRED]` *(Target: 15 early-career STEM job seekers)*.
* **Primary Signal**: Participant can accurately explain *why* a sample job was labeled "Stretch Opportunity" in $<30$ seconds.
* **Exit Criteria**: $\ge 85\%$ of participants correctly identify the primary addressable gap and locate the justifying resume citation without moderator prompting.

---

### Stage 3: Workflow Validation (Decision Velocity Benchmark)
* **Core Objective**: Benchmark the end-to-end decision loop (`Profile ➔ Ingest ➔ Fit Analysis ➔ Prioritize ➔ Save`) against the status quo workflow.
* **Uncertainty Reduced**: Proves whether AI Career Copilot reduces decision time from 30+ minutes to $<90$ seconds while preserving decision accuracy `[PRODUCT INFERENCE]`.
* **Method**: Usability lab benchmarking (`EXP-05`) with a standardized set of 10 technical job descriptions.
* **Participants Needed**: `[VALIDATION REQUIRED]` *(Target: 20 technical candidates)*.
* **Primary Signal**: Median Time-to-Decision (TTD) and Blocker Detection Accuracy.
* **Exit Criteria**: Median evaluation time per job drops below 90 seconds, and blocker detection accuracy reaches $\ge 90\%$.

---

### Stage 4: Cohort Pilot Validation (Multi-Week Retention & Context Retention)
* **Core Objective**: Test repeated product usage, pipeline Kanban maintenance, and context retrieval during live recruiter screening calls over a 3-week active search cycle.
* **Uncertainty Reduced**: Determines whether candidates build a habit around the product or abandon it after single-session novelty `[PRODUCT INFERENCE]`.
* **Method**: Closed beta release with telemetry instrumentation (`W-HCCD`, `PAR`, `ICRR`, `UER`).
* **Participants Needed**: `[VALIDATION REQUIRED]` *(Target: 50–75 active job seekers over 21 days)*.
* **Primary Signal**: **Weekly Active Decision-Makers (WADM)** and **Interview Context Retrieval Rate (ICRR)**.
* **Exit Criteria**: $\ge 40\%$ of activated pilot users return to execute $\ge 3$ triage decisions in Week 3; $>60\%$ of candidates reaching screening calls access the snapshot drawer.

---

### Stage 5: Controlled Experiments (Quantitative A/B Testing at Scale)
* **Core Objective**: Statistically validate causal lifts across variants for core product decisions (`EXP-01` through `EXP-04`).
* **Uncertainty Reduced**: Provides high-statistical-power proof of optimal feature mechanics.
* **Method**: Production A/B testing infrastructure with randomized cohort traffic allocation.
* **Participants Needed**: `[VALIDATION REQUIRED]` *(Requires minimum sample size determined by power analysis: $\alpha = 0.05, \beta = 0.80$)*.
* **Primary Signal**: Statistically significant lift in Decision Conviction Rate (DCR) and 7-day Queue Execution Rate (QER).
* **Exit Criteria**: Variant achieves statistically significant primary metric win while satisfying all AI safety guardrails.

---

## 3. Staged Validation Summary Matrix

| Validation Stage | Focus Level | Primary Method | Key Risk Addressed | Exit Milestone |
| :--- | :--- | :--- | :--- | :--- |
| **1. Problem** | Qualitative | Screen-share observations | Validating true candidate pain | $\ge 80\%$ confirmed JD confusion |
| **2. Prototype** | Usability | Think-aloud wireframe tests | Mental model comprehension | $\ge 85\%$ unprompted comprehension |
| **3. Workflow** | Benchmark | Timed lab task tests (`EXP-05`) | Decision velocity & accuracy | TTD $<90\text{s}$; Accuracy $\ge 90\%$ |
| **4. Pilot** | Cohort | 3-week closed beta telemetry | Habit & context retention | Week-3 Retention $\ge 40\%$ |
| **5. A/B Tests** | Quantitative | Controlled production tests | Causal feature optimization | Statistically significant DCR lift |
