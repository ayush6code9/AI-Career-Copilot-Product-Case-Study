# Opportunity Areas

This document translates diagnosed problem areas and root causes into structured **Opportunity Areas**.

> **Note**: These represent strategic problem spaces and potential value vectors, *not* finalized product features. Feature specification will occur during PRD definition.

---

## Strategic Opportunity Matrix

```
                     HIGH IMPACT
                          │
       OPP-02: Explainable│   OPP-03: Opportunity
       Fit Analysis       │   Prioritization
                          │
  ────────────────────────┼────────────────────────▶ MATURITY / COMPLEXITY
                          │
       OPP-01: Structured │   OPP-04: Skill Gap
       Relevance Ingestion│   Actionability
                          │
                      LOW IMPACT
```

---

## 1. Opportunity Area 1: Structured Relevance Assessment
* **User Problem**: Candidates waste substantial time opening listings that claim to be "Entry Level" but require multi-year commercial experience or unrelated tech stacks `[DESK RESEARCH]`.
* **Potential Value**: Reduces initial screening noise by surfacing roles matched against true baseline qualifications rather than superficial title tags `[PRODUCT INFERENCE]`.
* **Why It Matters**: Prevents search fatigue and preserves user cognitive energy for deep evaluation `[ASSUMPTION]`.
* **Evidence Level**: `[DESK RESEARCH]` (verified presence of inflated requirements on major job boards).
* **Key Assumption**: Early-career candidates prefer a smaller, high-relevance set of opportunities over exhaustive, uncurated job feeds `[ASSUMPTION]`.
* **What Needs Validation**: What minimum set of profile parameters (target roles, tools, graduation timeline) is required to deliver accurate initial relevance? `[HYPOTHESIS]`

---

## 2. Opportunity Area 2: Explainable Job-Fit Analysis
* **User Problem**: Existing platforms provide black-box percentage scores or keyword counters that fail to explain *why* a candidate is or isn't a viable match `[FACT]`.
* **Potential Value**: Transparent, multi-dimensional alignment analysis detailing:
  * Strong Matches (skills/projects directly proven in candidate profile)
  * Transferable Overlaps (academic/coursework equivalents)
  * Missing Requirements (differentiated into critical vs. secondary) `[PRODUCT INFERENCE]`.
* **Why It Matters**: Empowers candidates with objective conviction, mitigating imposter syndrome and eliminating blind guessing `[ASSUMPTION]`.
* **Evidence Level**: `[PRODUCT INFERENCE]` derived from candidate frustration with incumbent black-box algorithms.
* **Key Assumption**: Candidates trust and act upon qualitative breakdown explanations more than opaque numerical scores `[ASSUMPTION]`.
* **What Needs Validation**: How detailed must the explainability breakdown be to build user trust without causing cognitive overload? `[HYPOTHESIS]`

---

## 3. Opportunity Area 3: Intelligent Opportunity Prioritization
* **User Problem**: Candidates suffer from decision paralysis when managing dozens of open opportunities and fail to prioritize high-yield applications `[ASSUMPTION]`.
* **Potential Value**: Structured categorization of opportunities into actionable tiers (e.g., *Target Match*, *Reach / Stretch*, *Low Conviction*) based on holistic fit and candidate preferences `[PRODUCT INFERENCE]`.
* **Why It Matters**: Transforms a chaotic list of open browser tabs into an ordered, goal-oriented application queue `[PRODUCT INFERENCE]`.
* **Evidence Level**: `[ASSUMPTION]` based on candidate workflow observations.
* **Key Assumption**: Early-career candidates will follow recommended priority rankings rather than defaulting back to random or alphabetical applying `[ASSUMPTION]`.
* **What Needs Validation**: What weighting factors (skill overlap, role interest, deadline urgency) matter most in calculating priority? `[HYPOTHESIS]`

---

## 4. Opportunity Area 4: Actionable Skill-Gap Clarification
* **User Problem**: When candidates identify missing skills in a JD, they cannot tell whether the gap is an instant disqualifier or a minor tool they can learn rapidly `[ASSUMPTION]`.
* **Potential Value**: Dissects missing requirements by severity and suggests whether to apply with tailored narrative framing or pursue specific learning `[PRODUCT INFERENCE]`.
* **Why It Matters**: Increases candidate application rate on viable "stretch" roles where they would otherwise self-select out `[ASSUMPTION]`.
* **Evidence Level**: `[DESK RESEARCH]` on candidate self-selection behavior.
* **Key Assumption**: Clear gap categorization increases application confidence on 70–80% match opportunities `[ASSUMPTION]`.
* **What Needs Validation**: Can LLM-based reasoning accurately distinguish mandatory corporate prerequisites from flexible tool preferences across diverse companies? `[HYPOTHESIS]`

---

## 5. Opportunity Area 5: Unified Application Intelligence & Tracking
* **User Problem**: Job descriptions expire after postings close, leaving candidates with no reference when called for interviews; manual spreadsheet tracking has high abandonment `[FACT]`.
* **Potential Value**: Automated archival of the exact job description, fit analysis summary, and submission notes in a centralized pipeline view `[PRODUCT INFERENCE]`.
* **Why It Matters**: Closes the operational loop between discovery, evaluation, and interview preparation without requiring manual copy-pasting `[PRODUCT INFERENCE]`.
* **Evidence Level**: `[FACT]` (ephemeral nature of live job postings upon closing).
* **Key Assumption**: Storing the evaluated JD alongside the application status reduces interview preparation anxiety and prevents context loss `[ASSUMPTION]`.
* **What Needs Validation**: Will candidates keep their pipeline status updated if progression is semi-automated or prompted? `[HYPOTHESIS]`

---

## Summary Evaluation of Opportunity Areas

| Opportunity Area | Strategic Alignment | Expected User Value | Technical Feasibility | Validation Priority |
| :--- | :---: | :---: | :---: | :---: |
| **OPP-02: Explainable Fit Analysis** | High | Critical | High (LLM Extraction + Structured Taxonomy) | **P0 (Immediate Core)** |
| **OPP-03: Opportunity Prioritization** | High | Critical | High (Multi-Factor Scoring Logic) | **P0 (Immediate Core)** |
| **OPP-05: Unified Application Tracking** | High | High | Medium (CRUD Pipeline + Snapshot Storage) | **P0 (Immediate Core)** |
| **OPP-01: Structured Relevance Ingestion** | Medium | High | High (JD Parsing & Role Mapping) | **P1 (MVP Foundation)** |
| **OPP-04: Actionable Skill Gap Clarification** | High | Medium | Medium (Prompt Engineering & Ontology) | **P1 (Near-Term)** |
