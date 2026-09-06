# Root Cause Analysis

This document uses the **Problem Tree** framework and the **5 Whys** method to rigorously diagnose why early-career candidates experience severe decision friction and poor outcomes in their job search.

---

## 1. Problem Tree Analysis

```
                              ┌─────────────────────────────────────────────────────────┐
                              │                         EFFECTS                         │
                              │ • Candidate burnout & search paralysis                 │
                              │ • High volume of low-conviction, rejected applications  │
                              │ • High time wasted per application                      │
                              │ • Loss of context during recruiter screening calls      │
                              └────────────────────────────▲────────────────────────────┘
                                                           │
                              ┌─────────────────────────────────────────────────────────┐
                              │                      CORE PROBLEM                       │
                              │  Early-career candidates struggle to make informed,     │
                              │  confident, and prioritized job application decisions.  │
                              └────────────────────────────▲────────────────────────────┘
                                                           │
                 ┌─────────────────────────────────────────┼─────────────────────────────────────────┐
                 │                                         │                                         │
┌─────────────────────────────────┐       ┌─────────────────────────────────┐       ┌─────────────────────────────────┐
│     ROOT CAUSE CLUSTER 1:       │       │      ROOT CAUSE CLUSTER 2:      │       │      ROOT CAUSE CLUSTER 3:      │
│     JD Structural Ambiguity     │       │     Cognitive Evaluation Gap    │       │     Decisional & Tooling Gap    │
│                                 │       │                                 │       │                                 │
│ • Unstandardized requirements   │       │ • Asymmetric domain context     │       │ • Lack of objective priority    │
│ • "Wishlist" vs. mandatory blur │       │ • Project-to-JD translation gap │       │   frameworks                    │
│ • Inflated experience criteria  │       │ • Black-box job board matching  │       │ • Disconnected trackers & tabs  │
└─────────────────────────────────┘       └─────────────────────────────────┘       └─────────────────────────────────┘
```

---

## 2. 5 Whys Deep-Dive Analysis

### Chain A: Why do candidates resort to mass spray-and-pray applications?

1. **Why do candidates submit dozens of generic applications?**  
   Because they believe job search is purely a numbers game and lack confidence in which specific roles will respond `[ASSUMPTION]`.
2. **Why do they lack confidence in which roles will respond?**  
   Because they cannot accurately determine their true qualification match against listed job descriptions `[PRODUCT INFERENCE]`.
3. **Why can't they determine their qualification match?**  
   Because job descriptions list 15+ disparate tools, frameworks, and inflated experience requirements without indicating what is genuinely essential `[DESK RESEARCH]`.
4. **Why are job descriptions written this way?**  
   Because hiring managers and recruiters combine aspirational wishlists with generic compliance templates to cast a wide net or filter defensively `[DESK RESEARCH]`.
5. **Root Cause (Primary)**: **Structural Information Asymmetry & Non-Standardized Job Requirements** — candidates lack transparent, contextual translation of job requirements against their own unique academic and project background `[PRODUCT INFERENCE]`.

---

### Chain B: Why do candidates spend hours reviewing jobs without applying (Decision Paralysis)?

1. **Why do candidates keep 30+ browser tabs open without taking action?**  
   Because they cannot decide which 3–5 roles to invest time in tailoring applications for `[ASSUMPTION]`.
2. **Why can't they decide which 3–5 roles to prioritize?**  
   Because all roles appear equally plausible or equally intimidating on the surface `[ASSUMPTION]`.
3. **Why do all roles appear equally plausible or intimidating?**  
   Because job platforms only provide superficial keyword match badges (e.g., "Matched 4 of 6 skills") without explaining gap severity or project relevance `[FACT]`.
4. **Why don't current platforms provide deeper fit evaluation?**  
   Because incumbent platforms optimize their business models for employer candidate volume and sponsored listing monetization, not candidate decision quality `[PRODUCT INFERENCE]`.
5. **Root Cause (Primary)**: **Absence of Explainable Multi-Dimensional Fit & Prioritization Tooling** — candidate-facing decision intelligence does not exist on major job aggregators `[PRODUCT INFERENCE]`.

---

## 3. Classification: Primary vs. Secondary Causes

| Cause | Classification | Rationale & Evidence |
| :--- | :---: | :--- |
| **1. Opaque & Non-Standardized JDs** | **Primary Root Cause** | JDs fail to separate core prerequisites from preferences, making manual evaluation unreliable `[DESK RESEARCH]`. |
| **2. Lack of Explainable Fit Decision Tools** | **Primary Root Cause** | Current platforms offer black-box matching or keyword counters rather than contextual qualification analysis `[FACT]`. |
| **3. High Tool & Workflow Fragmentation** | **Secondary Cause** | Using disconnected tools (browsers, Google Sheets, ChatGPT) adds operational drag, but stems from the absence of an integrated decision hub `[PRODUCT INFERENCE]`. |
| **4. Time Scarcity (Academics + Job Hunt)** | **Secondary Cause** | Students have limited hours, but time pressure becomes critical primarily because evaluation and filtering are manual and inefficient `[ASSUMPTION]`. |
| **5. Lack of Candidate Self-Confidence** | **Secondary (Psychological) Cause** | Imposter syndrome is exacerbated directly by uncalibrated JD requirements and opaque rejections `[ASSUMPTION]`. |

---

## 4. Root Cause Hypotheses for Validation

* **Hypothesis RC-01**: If job descriptions are programmatically decomposed into Core Requirements vs. Preferred Signals, candidate evaluation time per posting will drop by >50% `[HYPOTHESIS]`.
* **Hypothesis RC-02**: If candidates receive explainable match reasoning (e.g., "Your PyTorch capstone satisfies the ML modeling requirement; Airflow is a preferred tool that can be learned on the job"), they will prioritize high-yield applications over mass-applying `[HYPOTHESIS]`.
* **Hypothesis RC-03**: Centralizing discovery, fit evaluation, and pipeline status into a unified workflow will reduce drop-off caused by spreadsheet maintenance friction `[HYPOTHESIS]`.
