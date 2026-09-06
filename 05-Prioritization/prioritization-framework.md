# Product Prioritization Framework & Methodology

This document defines the decision-making framework, scoring criteria, and governing prioritization principles used to evaluate product capabilities in **AI Career Copilot**.

---

## 1. Evaluation of Prioritization Frameworks

To establish a defensible, senior-level prioritization methodology, we evaluated five industry-standard prioritization frameworks against the specific needs of early-stage AI decision-support products:

| Framework | Core Mechanism | Strengths | Limitations in Early-Stage Products | Fit for AI Career Copilot |
| :--- | :--- | :--- | :--- | :---: |
| **RICE** *(Reach, Impact, Confidence, Effort)* | Quantitative formula: $\frac{R \times I \times C}{E}$ | Enforces balance between impact and effort; factors in confidence. | Often leads to false precision and fabricated numbers when real user counts are unavailable `[PRODUCT INFERENCE]`. | **Moderate (Adapted)** |
| **MoSCoW** *(Must, Should, Could, Won't)* | Categorical classification | Simple, intuitive stakeholder communication; sets hard MVP scope boundaries. | Lacks granular discrimination within categories; ignores dependency sequencing `[PRODUCT INFERENCE]`. | **High (For Scope Boundary)** |
| **Value vs. Effort Matrix** | 2x2 Matrix (Quick Wins, Major Bets, Fill-ins, Money Pits) | High visual clarity; fast strategic sorting. | Treats all features as independent; fails to capture architectural prerequisites `[FACT]`. | **Moderate** |
| **Value vs. Risk** | 2x2 Matrix (De-risking vs. Value) | Prioritizes solving core technical/AI uncertainties before scaling. | Does not account for operational dependencies. | **High (For AI Systems)** |
| **Dependency-Aware Prioritization** | Critical path & topological ordering | Ensures foundational data enablers are built before dependent customer features. | Needs to be paired with user value scoring. | **Critical (Mandatory Layer)** |

---

## 2. Selected Framework: Dependency-Aware Value-Risk Framework (DAVR)

> **Strategic Selection**: We adopt a **Dependency-Aware Value-Risk Framework (DAVR)**, utilizing a calibrated qualitative proxy scoring model adapted from RICE and Value/Risk matrices, layered over a strict topological dependency graph.

```
┌────────────────────────────────────────────────────────────────────────┐
│             DEPENDENCY-AWARE VALUE-RISK FRAMEWORK (DAVR)               │
├────────────────────────────────────────────────────────────────────────┤
│                                                                        │
│   1. VALUE MULTIPLIER:                                                 │
│      • User Impact: Direct reduction of decision friction (1 to 5)     │
│      • JTBD Alignment: Directness to core evaluation loop (1 to 3)     │
│                                                                        │
│   2. CONFIDENCE FACTOR:                                                │
│      • Grounded Evidence: Validated pain point vs. Assumption (0.5-1.0)│
│                                                                        │
│   3. EFFORT & COMPLEXITY:                                              │
│      • Relative Complexity: Engineering / AI uncertainty scale (1 to 5)│
│                                                                        │
│   4. DEPENDENCY GATE:                                                  │
│      • Hard Blocker: Cannot execute without prerequisite capability.   │
│                                                                        │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Dimension Definitions & Calibration Scales

To prevent pseudo-precision and avoid fabricating user counts, dimensions are defined using structured qualitative proxies:

### 3.1 User Impact (Score: 1 to 5)
Measures how substantially the capability reduces the candidate's cognitive overload, search fatigue, or context loss `[PRODUCT INFERENCE]`:
* **5 — Transformational**: Solves the core evaluation/decision bottleneck; enables the primary "Aha!" moment.
* **4 — High Value**: Substantially reduces operational friction or prevents application errors.
* **3 — Moderate Value**: Enhances workflow speed, usability, or presentation clarity.
* **2 — Low Value**: Minor convenience feature; secondary workflow polish.
* **1 — Negligible**: Cosmetic enhancement with minimal impact on decision quality.

### 3.2 JTBD Alignment (Multiplier: 1.0 to 1.5)
Measures how directly the capability fulfills the primary Job to Be Done (*"Instantly see a clear breakdown of how my skills and projects align with the role"*):
* **1.5 — Direct Core Driver**: Directly delivers explainable fit evaluation or priority ranking.
* **1.2 — Essential Enabler**: Upstream ingestion or downstream snapshot tracking required for the core loop.
* **1.0 — Peripheral / Ancillary**: Supporting utility feature.

### 3.3 Confidence Level (Factor: 0.5 to 1.0)
Measures the empirical certainty of the problem and technical feasibility from Phases 1–4:
* **1.0 — High Confidence**: Problem supported by verified industry mechanics (`[FACT]` / `[DESK RESEARCH]`).
* **0.8 — Medium Confidence**: Strong product deduction with low technical risk (`[PRODUCT INFERENCE]`).
* **0.5 — Low Confidence / Exploratory**: Unvalidated user hypothesis or high LLM extraction variability (`[HYPOTHESIS]`).

### 3.4 Relative Effort & Complexity (Score: 1 to 5)
Measures implementation complexity, AI prompt tuning difficulty, and edge-case handling:
* **1 — Low**: Simple UI state management, basic regex/metadata extraction.
* **2 — Moderate**: Standard CRUD workflows, local storage state persistence.
* **3 — Medium**: Structured LLM JSON schema extraction, multi-dimensional rule mapping.
* **4 — High**: Complex document parsing (unstructured PDFs), heuristic categorization engines.
* **5 — Very High**: Live web scraping across protected portals, browser automation.

---

## 4. Prioritization Tier Definitions

| Priority Tier | Label | Strategic Meaning & Action |
| :---: | :--- | :--- |
| **P0** | **Core MVP (Must Build)** | Essential capabilities without which the core decision-support value proposition cannot function. Non-negotiable for release. |
| **P1** | **Important Enablers (Should Build)** | Critical friction reducers and trust builders that significantly enhance MVP usability and conversion. |
| **P2** | **Near-Term Enhancements (Defer to Post-MVP)** | Valuable capabilities that expand utility but are not required to test the core decision-support hypothesis. |
| **P3** | **Explicit Non-Goals (Won't Build / Reject)** | Capabilities intentionally rejected to prevent ecosystem spam, maintain candidate agency, and avoid scope creep. |

---

## 5. Core Prioritization Principles

These 6 governing principles dictate all prioritization decisions in **AI Career Copilot**:

```
┌────────────────────────────────────────────────────────────────────────┐
│                     GOVERNING PRIORITIZATION PRINCIPLES                │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Prioritize Core Decision Bottlenecks Over Peripheral Convenience    │
│ 2. Prioritize Transparent Evidence & Trust Before Workflow Automation  │
│ 3. Resolve Foundational AI Uncertainty Before Expanding Feature Breadth│
│ 4. Build Minimum Input Enablers First (Topological Dependencies)       │
│ 5. Say NO to High-Activity Automation That Degrades Decision Quality   │
│ 6. Prefer Capabilities That Produce Reusable Product Learning          │
└────────────────────────────────────────────────────────────────────────┘
```

### Principle 1: Prioritize Core Decision Bottlenecks Over Peripheral Convenience
* **Rationale**: If the candidate cannot accurately evaluate whether they qualify for a role, convenient features like calendar integrations or cover letter generators provide zero baseline value `[PRODUCT INFERENCE]`.

### Principle 2: Prioritize Transparent Evidence & Trust Before Workflow Automation
* **Rationale**: Early-career candidates naturally distrust black-box AI scores. Providing inspectable evidence tooltips and transparent gap severity tiers takes priority over automated one-click shortcuts `[PRODUCT INFERENCE]`.

### Principle 3: Resolve Foundational AI Uncertainty Before Expanding Feature Breadth
* **Rationale**: We must prove that LLMs can reliably parse technical JDs and map project evidence for 5 core technical roles before attempting horizontal expansion to non-technical domains `[PRODUCT INFERENCE]`.

### Principle 4: Build Minimum Input Enablers First
* **Rationale**: High-value features downstream (e.g., Kanban tracking and Opportunity Queues) strictly require clean upstream candidate profile data and structured JD entities `[FACT]`.

### Principle 5: Say NO to High-Activity Automation That Degrades Decision Quality
* **Rationale**: We strictly reject building auto-apply bots. Features that increase vanity activity (spam submissions) while decreasing candidate interview readiness directly violate our strategic mission `[PRODUCT INFERENCE]`.

### Principle 6: Prefer Capabilities That Produce Reusable Product Learning
* **Rationale**: Every capability in the initial release must test a core product hypothesis (e.g., do qualitative tiers improve application conviction vs. scores?) to guide subsequent roadmap decisions `[PRODUCT INFERENCE]`.

---

## 6. Limitations of the Prioritization Model

1. **Absence of Live Telemetry**: As a pre-launch case study, scoring relies on qualitative proxies and structural problem severity rather than production clickstream analytics `[FACT]`.
2. **Dynamic LLM Performance**: Technical effort scores may fluctuate as underlying model capabilities and prompt-engineering patterns evolve `[ASSUMPTION]`.
