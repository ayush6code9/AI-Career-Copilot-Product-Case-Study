# Metrics Decision Log

This document records the foundational telemetry and measurement decisions, alternative evaluations, and revisit triggers established for **AI Career Copilot**.

---

## 1. Decision Log Architecture

```
┌────────────────────────────────────────────────────────────────────────┐
│                        METRICS DECISION LOG                            │
├────────────────────────────────────────────────────────────────────────┤
│ MD-01: North Star Focuses on Decision Value Rather Than Job Volume     │
│ MD-02: AI Quality & Grounding Tracked Independently from Usage Metrics │
│ MD-03: Evidence Citation Inspection Measured as a Core Health Signal   │
│ MD-04: User Correction Rate Tracked as a Primary Feedback Signal       │
│ MD-05: Application Submission Volume Excluded as North Star Metric     │
│ MD-06: Guardrail Metrics Mandated to Prevent Misleading Optimization   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Structured Decision Records

### Decision MD-01: North Star Focuses on Decision Value Rather Than Job Volume
* **Context**: What single metric best captures value delivery for early-career job seekers navigating fragmented markets?
* **Alternatives Considered**:
  * *Option A*: Total Job Descriptions Analyzed per User.
  * *Option B*: Weekly High-Confidence Career Decisions (W-HCCD: deliberate triage actions following qualified review).
* **Evaluation**: Option A measures AI compute consumption and rewards browsing paralysis; Option B directly measures candidate cognitive breakthroughs and committed action `[PRODUCT INFERENCE]`.
* **Decision**: **Adopt Weekly High-Confidence Career Decisions (W-HCCD) as North Star (Option B).**
* **Rationale**: The core customer problem is decision paralysis. An outcome where a candidate reviews 5 roles and makes 5 clear decisions (e.g., 2 applied, 3 discarded with blocker notes) is far superior to analyzing 50 roles with zero conviction `[FACT]`.
* **Consequence**: Product roadmap and sprint goals optimize for decision velocity and conviction rather than infinite scrolling feeds.
* **Revisit Trigger**: Revisit if qualitative user interviews indicate candidates value ambient exploratory browsing more than decisive triage.

---

### Decision MD-02: AI Quality & Grounding Tracked Independently from Usage
* **Context**: Should AI model performance be evaluated solely through user adoption (retention, click-through) or through explicit quality telemetry?
* **Alternatives Considered**:
  * *Option A*: Measure AI success through session frequency and feature adoption alone.
  * *Option B*: Instrument dedicated AI quality metrics (Unsupported Evidence Rate, Extraction Accuracy, Ambiguity Detection).
* **Evaluation**: In generative AI systems, high usage can occur alongside severe hallucinations (automation bias), leading to delayed churn when candidates are rejected from misaligned interviews `[DESK RESEARCH]`.
* **Decision**: **Mandate Independent AI Quality Telemetry (Option B).**
* **Rationale**: Grounding fidelity is a safety prerequisite. We must track whether generated claims map directly to candidate profile text to protect candidate reputation `[PRODUCT INFERENCE]`.
* **Consequence**: Telemetry pipeline logs prompt extraction accuracy and match grounding rates on every analysis.
* **Revisit Trigger**: None. Strict ethical and product quality mandate.

---

### Decision MD-03: Evidence Citation Inspection Measured as a Core Health Signal
* **Context**: Why should the system track whether candidates hover over or click evidence citation tooltips?
* **Alternatives Considered**:
  * *Option A*: Treat tooltips as purely cosmetic UI elements without dedicated telemetry.
  * *Option B*: Track Evidence Inspection Rate (EIR) as a key diagnostic of user trust and auditability.
* **Evaluation**: If users ignore evidence citations, it either indicates complete trust (or automation bias) or that citations are poorly formatted. Tracking EIR reveals how users consume explainability `[PRODUCT INFERENCE]`.
* **Decision**: **Track Evidence Inspection Rate as a Primary Diagnostic (Option B).**
* **Rationale**: Transparent explainability is our core strategic differentiator (`Pillar 1`). Monitoring interaction with citations proves whether users value evidence-backed reasoning `[PRODUCT INFERENCE]`.
* **Consequence**: Requires frontend event debouncing on hover/click states.
* **Revisit Trigger**: If EIR remains static across all user cohorts, evaluate simplifying tooltip design to inline text.

---

### Decision MD-04: User Correction Rate Tracked as a Primary Feedback Signal
* **Context**: When a candidate edits an auto-extracted skill or overrides an AI priority tier, how should the product team interpret this action?
* **Alternatives Considered**:
  * *Option A*: Treat manual edits as user friction or operational failure.
  * *Option B*: Treat manual edits as a valuable quality calibration signal for prompt tuning and ontology refinement.
* **Evaluation**: In an AI co-pilot model, user corrections represent active candidate agency and provide ground-truth training signals to improve extraction rules `[PRODUCT INFERENCE]`.
* **Decision**: **Track AI Correction Rate as an Optimization Signal (Option B).**
* **Rationale**: High correction rates pinpoint specific technical terms or non-traditional project formats where the parser struggles, guiding targeted prompt engineering `[PRODUCT INFERENCE]`.
* **Consequence**: Telemetry captures diffs on edited skills without logging private PII.
* **Revisit Trigger**: If correction rates exceed 15% on standard CS/analytics resumes, trigger immediate prompt overhaul.

---

### Decision MD-05: Application Submission Volume Excluded as North Star Metric
* **Context**: Why shouldn't total applications submitted be the primary metric for a career platform?
* **Alternatives Considered**:
  * *Option A*: Adopt "Total Applications Submitted" as the North Star.
  * *Option B*: Measure "Prioritized Application Progression Rate" as a supporting outcome, keeping decision quality as the North Star.
* **Evaluation**: Optimizing for raw application volume drives product teams to build one-click spam bots, degrading application quality, harming candidate preparation, and flooding recruiters `[DESK RESEARCH]`.
* **Decision**: **Explicitly Exclude Raw Application Volume as North Star (Option B).**
* **Rationale**: AI Career Copilot exists to eliminate spray-and-pray. Success is high-conviction time allocation and higher interview conversion, not higher rejection volume `[PRODUCT INFERENCE]`.
* **Consequence**: The team is evaluated on decision quality and triage velocity, never on raw application counts.
* **Revisit Trigger**: Non-negotiable. Core to product positioning and philosophy.

---

### Decision MD-06: Guardrail Metrics Mandated to Prevent Misleading Optimization
* **Context**: How do we ensure that increasing decision velocity does not accidentally degrade recommendation accuracy?
* **Alternatives Considered**:
  * *Option A*: Track only positive conversion funnels (growth metrics).
  * *Option B*: Implement explicit Guardrail Metrics (False Positive Rate, Zero-Second Triage Rate, Ingestion Error Rate) with investigation thresholds.
* **Evaluation**: Growth metrics without guardrails lead to optimizing for addictive or superficial behaviors (e.g. users clicking "Queue" without reading) `[PRODUCT INFERENCE]`.
* **Decision**: **Establish 5 Core Guardrail Metrics (Option B).**
* **Rationale**: Guardrails ensure that product changes which improve speed do not compromise AI grounding or user comprehension `[PRODUCT INFERENCE]`.
* **Consequence**: Sprint releases must pass guardrail checks before full cohort rollout.
* **Revisit Trigger**: Review guardrail trigger thresholds quarterly as user sample sizes grow.
