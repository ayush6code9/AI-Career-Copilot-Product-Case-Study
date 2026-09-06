# Product Metrics Framework & Telemetry Philosophy

This document defines the overarching measurement architecture, metric hierarchy, and product telemetry philosophy for **AI Career Copilot**.

---

## 1. Metrics Philosophy: Value Over Vanity

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CORE METRIC PHILOSOPHY                          │
├────────────────────────────────────────────────────────────────────────┤
│ • Activity ≠ Value (100 jobs analyzed with zero action = zero value). │
│ • Application Volume ≠ Success (More applications can mean more spam). │
│ • AI Usage ≠ AI Quality (A flawed AI model can still be heavily used). │
│ • Time Spent ≠ Engagement (Long sessions often signal confusion).      │
│ • Trust & Grounding are Mandatory Prerequisites for Retention.         │
└────────────────────────────────────────────────────────────────────────┘
```

### 1.1 Why Activity Is Not Value
In conventional job-search platforms, engagement is measured by vanity volume: page views, searches performed, and raw applications submitted `[FACT]`. In a career decision-support product, high activity often signals user distress—a candidate frantically analyzing 50 jobs in an evening is experiencing search fatigue and decision paralysis (`PP-07`), not high product satisfaction `[PRODUCT INFERENCE]`.

### 1.2 Why Job Application Volume Is Misleading
Maximizing raw application count incentivizes spray-and-pray behaviors that flood recruiters with low-intent resumes, damages candidate brand, and yields near-zero interview conversion `[DESK RESEARCH]`. AI Career Copilot measures **Decision Quality and High-Conviction Time Allocation**, prioritizing focused, high-yield applications over blind submission volume.

### 1.3 Why AI Products Require Trust & Grounding Metrics
Unlike deterministic SaaS tools, generative AI applications face unique failure modes: hallucinations, false confidence, and uncalibrated ambiguity `[FACT]`. Measuring standard adoption without monitoring **grounding rates, evidence inspection, and user correction rates** risks optimizing for an inaccurate model that users will ultimately abandon `[PRODUCT INFERENCE]`.

---

## 2. Five-Level Metric Hierarchy

```
┌────────────────────────────────────────────────────────────────────────┐
│                       1. NORTH STAR METRIC                             │
│   Weekly High-Confidence Career Decisions Completed (W-HCCD)           │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ decomposes into
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                    2. PRIMARY OUTCOME METRICS                          │
│ • Decision Velocity (Time to Decision) • Qualification Conviction Rate │
│ • High-Fit Opportunity Conversion Rate • Context Retrieval Rate        │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ supported by
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                    3. PRODUCT HEALTH METRICS                           │
│ • Profile Activation Rate (D1)         • Weekly Active Decision Makers │
│ • Pipeline Stage Progression Rate      • Snapshot Archival Rate        │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ diagnosed via
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     4. DIAGNOSTIC METRICS                              │
│ • Ingestion Mode Ratio (Paste vs URL)  • Evidence Tooltip Hover Rate   │
│ • Gap Severity Distribution            • Priority Override Rate        │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ protected by
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     5. GUARDRAIL METRICS                               │
│ • False Positive Recommendation Rate   • Hallucinated Evidence Rate    │
│ • Ambiguity Warning Ignored Rate       • System Failure Rate (<1%)     │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Metric Hierarchy Breakdown across 9 Functional Dimensions

| Dimension | Metric Level | Primary Focus & Intent | Key Metric Example |
| :--- | :--- | :--- | :--- |
| **1. Activation** | Product Health | Measures zero-friction onboarding and profile readiness. | **Profile Activation Rate (PAR)**: % of signups who complete baseline verification in <60s `[DESIGN TARGET]`. |
| **2. Decision Quality** | Primary Outcome | Measures whether candidate decisions are grounded in objective qualification fit. | **High-Fit Acceptance Rate (HFAR)**: % of recommended High-Fit roles accepted into Priority Queue. |
| **3. Decision Velocity** | Primary Outcome | Measures reduction in cognitive time required to evaluate a job description. | **Median Time-to-Decision (TTD)**: Time from JD ingestion to triage action (<90s target) `[DESIGN TARGET]`. |
| **4. Explainability & Trust**| Diagnostic / Health | Measures candidate engagement with underlying AI evidence citations. | **Evidence Inspection Rate (EIR)**: % of evaluated roles where candidate inspects evidence tooltips. |
| **5. Prioritization** | Primary Outcome | Measures candidate focus on top-tier opportunities vs. low-signal roles. | **Queue Execution Rate (QER)**: % of Prioritized Tier 1 roles that progress to official application. |
| **6. Tracking & Context** | Product Health | Measures context preservation and elimination of 404 broken link anxiety. | **Interview Context Retrieval Rate (ICRR)**: % of active interview stages where snapshot drawer is accessed. |
| **7. Retention & Loyalty** | Product Health | Measures ongoing workflow stickiness throughout the multi-week job hunt. | **Weekly Active Decision-Makers (WADM)**: Candidates who execute ≥3 meaningful triage actions weekly. |
| **8. AI Quality & Safety** | Guardrail | Measures grounding fidelity, extraction accuracy, and hallucination absence. | **Unsupported Evidence Rate (UER)**: % of generated match claims that lack direct candidate profile proof. |
| **9. System Reliability** | Guardrail | Measures technical uptime and error-free ingestion across text and URLs. | **Ingestion Failure Rate (IFR)**: % of JD inputs that error out or fail entity extraction. |

---

## 4. Guardrail Metrics & Investigation Triggers

Guardrails prevent the team from gaming engagement metrics at the expense of user value or AI safety:

| Guardrail ID | Risk Guarded Against | Measurement Metric | Investigation Trigger Threshold | Corrective Action |
| :--- | :--- | :--- | :---: | :--- |
| **GR-01** | **False Positive Match Inflation** (AI telling unqualified users to apply) | User Rejection Rate on High-Fit recommendations | `[VALIDATION REQUIRED]` *(Initial target: >25% override)* | Audit prompt ontology; calibrate prerequisite weights. |
| **GR-02** | **Hallucinated Evidence Claims** (AI inventing unstated candidate skills) | User-Reported Unsupported Match Rate | `[VALIDATION REQUIRED]` *(Initial target: >2% of claims)* | Enforce stricter JSON schema extraction temperature zero. |
| **GR-03** | **Automation Bias / Blind Acceptance** (Users accepting AI tiers without reading) | Zero-Second Triage Rate (<5s review before saving) | `[VALIDATION REQUIRED]` *(Initial target: >35% of actions)* | Introduce visual friction; highlight key gaps before queueing. |
| **GR-04** | **Ingestion Failure & Scraper Breakage** | Ingestion Error Rate (URL/Text extraction failure) | `[VALIDATION REQUIRED]` *(Initial target: >5% failure)* | Inspect scraping proxy; prompt 1-click text paste fallback. |
| **GR-05** | **Pipeline Abandonment (Spreadsheet Relapse)** | Inactive Pipeline Ratio (Cards static for >21 days) | `[VALIDATION REQUIRED]` *(Initial target: >40% cards)* | Trigger follow-up reminders and interview prep nudges. |

---

## 5. Metric Anti-Patterns: What We Deliberately DO NOT Optimize

```
┌────────────────────────────────────────────────────────────────────────┐
│                        METRIC ANTI-PATTERNS                            │
├────────────────────┬───────────────────────────────────────────────────┤
│ ANTI-PATTERN       │ WHY IT IS HARMFUL & MISLEADING                    │
├────────────────────┼───────────────────────────────────────────────────┤
│ 1. Raw Application │ Incentivizes spam bot behavior, lowers candidate  │
│    Volume Count    │ interview readiness, and harms hiring ecosystem.   │
├────────────────────┼───────────────────────────────────────────────────┤
│ 2. Total AI Runs / │ Measures model API consumption, not whether the   │
│    Tokens Spent    │ user received actionable decision clarity.         │
├────────────────────┼───────────────────────────────────────────────────┤
│ 3. Time Spent on   │ Longer session duration often signals confusion,  │
│    Evaluation Card │ uncalibrated ambiguity, or cognitive fatigue.     │
├────────────────────┼───────────────────────────────────────────────────┤
│ 4. Total Jobs      │ Parsing 100 jobs without making a decision        │
│    Ingested        │ represents browsing paralysis, not user value.    │
└────────────────────┴───────────────────────────────────────────────────┘
```
