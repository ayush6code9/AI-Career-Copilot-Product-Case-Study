# Experiment Designs & Protocol Specifications

This document defines the formal experiment protocols, variant specifications, primary metrics, guardrails, and decision rules for testing the five core product hypotheses of **AI Career Copilot**.

---

## Experiment Index

```
┌────────────────────────────────────────────────────────────────────────┐
│ 1. EXP-01: Qualitative Fit Tiers vs. Single Numerical Match Score      │
│ 2. EXP-02: Evidence-First Architecture vs. Summary-First UI            │
│ 3. EXP-03: Raw JD Text Ingestion vs. Live URL Web Scraping             │
│ 4. EXP-04: System-Generated 3-Tier Queue vs. Manual Triage             │
│ 5. EXP-05: Core Product Value: Copilot Loop vs. Disjointed Status Quo  │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Experiment EXP-01: Qualitative Fit Tiers vs. Numerical Match Scores

* **Strategic Context**: Validates our core UX decision to reject percentage wheels (`78% Match`) in favor of 5 qualitative tiers (*Strong Fit*, *Reasonable Fit*, *Stretch*, *Low Fit*, *Insufficient Info*).
* **Falsifiable Hypothesis**: `[HYPOTHESIS]` Candidates presented with qualitative fit tiers will demonstrate higher decision conviction and lower evaluation hesitation than candidates presented with a single numerical match score.
* **Target Audience**: Active early-career job seekers evaluating technical and analytical postings.
* **Variant Architecture**:
  * **Control (Variant A - Numerical)**: Job card renders a circular percentage badge (e.g., *"82% Match"*) with standard skill lists.
  * **Treatment (Variant B - Qualitative)**: Job card renders 5 qualitative tiers (*Strong Fit*, *Reasonable Fit*, *Stretch Opportunity*, *Low Fit*, *Insufficient Info*) paired with 3-bucket requirement breakdown.
* **Metric Hierarchy**:
  * **Primary Metric**: **Decision Conviction Rate (DCR)** — % of viewed evaluations ending in an explicit triage action (`Prioritized`, `Saved`, or `Discarded`).
  * **Secondary Metrics**: Median dwell time before decision; % of *Stretch* opportunities accepted.
  * **Guardrail Metrics**:
    * User-Reported Mismatch Rate: Must not exceed 2.0% `[VALIDATION REQUIRED]`.
    * False Confidence Override Rate: Must remain <5.0% `[VALIDATION REQUIRED]`.
* **Decision Rules**:
  * *Strongly Positive*: If Variant B increases DCR by $\ge 10\%$ with no increase in mismatch rate $\rightarrow$ Permanently lock qualitative tiers across platform.
  * *Neutral / Mixed*: If DCR is identical but qualitative feedback favors visual simplicity $\rightarrow$ Test hybrid tier with secondary qualitative strength bar.
  * *Negative*: If Variant A produces $\ge 15\%$ higher decision velocity with equal accuracy $\rightarrow$ Re-evaluate numerical score implementation.
* **Product Learning Generated**: Validates whether early-career candidates benefit more from transparent qualitative reasoning than mathematical pseudo-precision `[PRODUCT INFERENCE]`.

---

## 2. Experiment EXP-02: Evidence-First Architecture vs. Summary-Only UI

* **Strategic Context**: Tests whether grounding AI assertions in verified candidate resume bullets increases user trust and auditability.
* **Falsifiable Hypothesis**: `[HYPOTHESIS]` Displaying explicit project citations adjacent to requirements will increase candidate confidence and decrease hallucination skepticism compared to rendering a high-level summary narrative.
* **Variant Architecture**:
  * **Control (Variant A - Summary First)**: Renders a 3-bullet AI text summary; evidence citations are collapsed inside a nested secondary menu.
  * **Treatment (Variant B - Evidence First)**: Renders the 3-bucket requirement breakdown with inline inspectable evidence chips citing verified resume bullets front-and-center.
* **Metric Hierarchy**:
  * **Primary Metric**: **Evidence Inspection Rate (EIR)** — % of evaluations where candidate inspects citations.
  * **Secondary Metrics**: Time-to-Decision (TTD); return cohort retention.
  * **Guardrail Metric**: Total cognitive review time must not exceed 120 seconds `[DESIGN TARGET]`.
* **Decision Rules**:
  * *Positive*: If Variant B achieves $\ge 35\%$ EIR and TTD remains $<90\text{s}$ $\rightarrow$ Enforce evidence-first layout as standard design pattern.
  * *Negative*: If Variant B causes TTD to exceed 180s due to cognitive clutter $\rightarrow$ Refine citations into hover popovers.
* **Product Learning Generated**: Proves whether early-career candidates act as active auditors who demand proof before trusting AI recommendations `[PRODUCT INFERENCE]`.

---

## 3. Experiment EXP-03: Raw JD Text Ingestion vs. Live URL Web Scraping

* **Strategic Context**: Validates our decision to prioritize 1-click text pasting as the P0 entry point over fragile web scrapers.
* **Falsifiable Hypothesis**: `[HYPOTHESIS]` Defaulting to 1-click raw text pasting will produce a significantly higher ingestion success rate and lower drop-off than defaulting to URL scraping on gated platforms.
* **Variant Architecture**:
  * **Control (Variant A - URL Default)**: Default ingestion interface opens with a URL input field; text paste is tucked behind a secondary tab.
  * **Treatment (Variant B - Paste Default / Hybrid)**: Default interface opens with a prominent multi-line text paste box with a 1-click sample button; URL scraping is a secondary tab.
* **Metric Hierarchy**:
  * **Primary Metric**: **First Ingestion Completion Rate (FICR)** — % of activated profiles that successfully structure a JD in their first session.
  * **Secondary Metrics**: Ingestion error rate (403/404/login wall errors); time to ingest.
  * **Guardrail Metric**: User qualitative satisfaction score on ingestion ease.
* **Decision Rules**:
  * *Positive*: If Variant B achieves $\ge 95\%$ completion vs. $<75\%$ for Variant A due to login wall blocks on LinkedIn/Handshake $\rightarrow$ Retain paste-first hybrid as permanent P0 interface.
* **What We Learn**: Quantifies the true failure rate of external URL scraping across real-world candidate job portals `[PRODUCT INFERENCE]`.

---

## 4. Experiment EXP-04: System-Generated 3-Tier Queue vs. Manual Triage

* **Strategic Context**: Tests whether automated priority grouping reduces decision paralysis while preserving user agency.
* **Falsifiable Hypothesis**: `[HYPOTHESIS]` Automatically organizing analyzed jobs into a 3-tier priority queue (High Fit, Stretch, Low Conviction) will reduce triage time and increase 7-day application follow-through compared to an unranked list.
* **Variant Architecture**:
  * **Control (Variant A - Flat List)**: Evaluated jobs are saved into a single chronological list; candidate manually tags priority.
  * **Treatment (Variant B - 3-Tier Queue)**: System automatically segments opportunities into Tier 1 (High Fit), Tier 2 (Stretch), and Tier 3 (Low Match), with full drag-and-drop manual override.
* **Metric Hierarchy**:
  * **Primary Metric**: **7-Day Queue Execution Rate (QER)** — % of prioritized Tier 1 opportunities submitted on official employer portals.
  * **Secondary Metrics**: Median session triage time; manual priority override frequency.
  * **Guardrail Metric**: Automation Bias Rate (candidate blindly accepting Low Fit roles without review must remain $<5\%$).
* **Decision Rules**:
  * *Positive*: If Variant B increases 7-day application conversion by $\ge 20\%$ and reduces triage time by $\ge 30\%$ $\rightarrow$ Scale 3-tier queue architecture.
* **What We Learn**: Proves whether structured triage directly unlocks focused application momentum `[PRODUCT INFERENCE]`.

---

## 5. Experiment EXP-05: Core End-to-End Product Value Experiment

> **The Central Research Question**:  
> **"Does AI Career Copilot actually improve early-career candidate decision velocity, qualification conviction, and application efficiency compared to the status quo workflow (LinkedIn + ChatGPT + Google Sheets)?"**

```
┌────────────────────────────────────────────────────────────────────────┐
│                   EXP-05: CORE PRODUCT VALUE BENCHMARK                 │
├────────────────────────────────────────────────────────────────────────┤
│ WORKFLOW A (Status Quo Baseline):                                      │
│ Browse LinkedIn/Indeed ➔ Read Bloated JDs ➔ Copy-Paste into ChatGPT    │
│ ➔ Mental Fit Guesswork ➔ Manually Log into Google Sheets.              │
│                                                                        │
│ WORKFLOW B (AI Career Copilot Integrated Loop):                        │
│ Profile Baseline ➔ Ingest JD ➔ Explainable Fit Breakdown               │
│ ➔ 3-Tier Prioritization ➔ 1-Click Snapshot Kanban Pipeline.           │
└────────────────────────────────────────────────────────────────────────┘
```

* **Experimental Design**: Within-subject benchmark study with a cohort of final-year technical candidates evaluating a standardized set of 10 entry-level job descriptions (5 High-Fit, 3 Stretch, 2 Low-Fit with hidden blockers) `[HYPOTHESIS]`.
* **Primary Evaluation Metrics**:
  1. **Evaluation Velocity**: Total time required to evaluate all 10 opportunities and commit triage actions. `[DESIGN TARGET: <15 mins on Copilot vs. >60 mins on Status Quo]`.
  2. **Decision Accuracy & Conviction**: % of candidates who correctly identify hidden fatal blockers (e.g. 3-year commercial exp or missing visa eligibility) before applying.
  3. **Interview Context Retention**: Ability to retrieve exact JD requirements and relevant project talking points during a simulated recruiter screening call 2 weeks later.
* **Guardrails & Safety**:
  * Candidate must not experience cognitive fatigue score increase (measured via post-task NASA-TLX survey) `[DESIGN TARGET]`.
* **Decision Rule & Strategic Threshold**:
  * *Success Trigger*: If AI Career Copilot achieves $\ge 50\%$ reduction in evaluation time while simultaneously improving blocker detection accuracy by $\ge 30\%$ $\rightarrow$ Full strategic validation of the core product value proposition.
* **What We Learn**: Proves whether consolidated decision intelligence creates defensible utility over disconnected horizontal tools `[PRODUCT INFERENCE]`.

---

## 6. Experiment Prioritization Matrix

| Experiment ID | Core Problem Tested | User Impact | Uncertainty Level | Engineering Effort | Learning Value | Execution Priority |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: |
| **EXP-05** | **Core Value Proposition vs Status Quo** | Critical | High | Medium | **Maximum** | **P0 (First Validation)** |
| **EXP-01** | **Qualitative Tiers vs. Percentage Scores** | Critical | High | Low | **High** | **P0 (MVP Launch Gate)** |
| **EXP-02** | **Evidence Citations & Trust Grounding** | High | Medium | Low | **High** | **P0 (MVP Launch Gate)** |
| **EXP-03** | **Raw Text Paste vs URL Ingestion** | High | Low | Low | **Medium** | **P1 (Sprint 1 Test)** |
| **EXP-04** | **3-Tier Queue vs Flat List** | Medium | Medium | Low | **Medium** | **P1 (Sprint 2 Test)** |
