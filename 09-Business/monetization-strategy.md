# Monetization Strategy & Tier Architecture

## Executive Summary

The **Monetization Strategy** establishes the value boundaries, feature gating logic, and pricing structure for AI Career Copilot under the recommended Freemium B2C model.

A foundational principle governing this strategy is that **core decision honesty is never paywalled**. Free users receive complete, uncompromised fit analyses and gap severity evaluations. Premium subscriptions monetize **workflow volume, deep portfolio artifact ingestion, advanced interview preparation tooling, and multi-track search management**.

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   MONETIZATION TIER BOUNDARIES                                   │
│                                                                                                  │
│   FREE DECISION TIER ($0 / Forever)             PREMIUM COPILOT PRO ($15/mo `[PLANNING ASSUMPTION]`)│
│   ┌────────────────────────────────────────┐    ┌─────────────────────────────────────────────┐  │
│   │ Complete Decision Evaluation           │    │ Full Workflow & Interview Power             │  │
│   │ • 100% Honest Fit Breakdown            │    │ • Everything in Free Tier                   │  │
│   │ • 5 Qualitative Fit Tiers              │    │ • Unlimited Ingestion & Stored Snapshots    │  │
│   │ • 4-Category Requirement Taxonomy      │ ─▶ │ • Deep GitHub Code & SQL Project Ingestion  │  │
│   │ • Gap Severity Classification          │    │ • STAR-Method Interview Answer Generator    │  │
│   │ • Up to 15 Active Tracked Snapshots    │    │ • Multi-Track Profile Linking (e.g. DS & SWE│  │
│   │ • 5 New JD Analyses per Week           │    │ • Market Skill Demand Drift Radar           │  │
│   └────────────────────────────────────────┘    └─────────────────────────────────────────────┘  │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Free vs. Premium Tier Specifications

| Feature / Capability | Free Decision Tier ($0) | Premium Copilot Pro ($15/mo `[PLANNING ASSUMPTION]`) | Strategic Rationale for Gating |
| :--- | :---: | :---: | :--- |
| **Candidate Profile Parsing** | Standard Resume PDF (1 Version) | Multi-Version Profiles (Up to 3 Tracks) | Free covers single search; multi-track serves power seekers. |
| **Raw JD Text Ingestion** | Up to 5 JDs / Week | **Unlimited JDs** | Free supports thoughtful selective search; Pro supports high volume. |
| **4-Category Requirement Taxonomy** | **Included (Full)** | **Included (Full)** | Core decision structuring must remain accessible to all. |
| **5 Qualitative Fit Tiers** | **Included (Full)** | **Included (Full)** | Calibrated tiering is core value; never degraded. |
| **Demonstrated Match Quote Citations** | **Included (Full)** | **Included (Full)** | Truth and grounding are never paywalled. |
| **4-Level Skill Gap Classification** | **Included (Full)** | **Included (Full)** | Helping candidates avoid bad fits is free core value. |
| **3-Tier Opportunity Triage Queue** | **Included (Full)** | **Included (Full)** | Essential for candidate decision agency. |
| **Immutable Local JD Snapshot Archive** | Up to 15 Stored Jobs | **Unlimited Stored Archives** | Heavy archive storage incurs infrastructure cost. |
| **Kanban Application Tracker** | Basic Kanban (15 Cards) | **Unlimited Kanban + History** | Power organization tool for active multi-interview pipelines. |
| **Interview Preparation Context Drawer** | Basic Talking Points | **Full STAR-Method Answer Frameworks** | Advanced interview prep delivers high willingness-to-pay. |
| **GitHub / SQL Project Deep Ingestion** | Not Included | **Included (Deep Code Parsing)** | High-compute AI feature tailored to serious tech candidates. |
| **Market Skill Demand Drift Alerts** | Not Included | **Included (Longitudinal Radar)** | Long-term macro insight for proactive career development. |

---

## 2. Upgrade Triggers & Conversion Mechanics

Conversion from Free to Premium is triggered naturally when candidate search intensity and interview progression increase:

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   NATURAL UPGRADE TRIGGERS                                       │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 1. PIPELINE CAPACITY TRIGGER                                                                     │
│    Candidate evaluates their 16th job posting and hits the 15-snapshot free storage ceiling.    │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 2. INTERVIEW INVITATION TRIGGER                                                                  │
│    Candidate transitions a tracked role to "Interviewing" and unlocks the STAR-method prep      │
│    talking points generator for specific role-gap questions.                                    │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 3. DUAL-TRACK SEARCH TRIGGER                                                                     │
│    Candidate decides to apply for both Data Analyst and Junior Software Engineer roles and needs │
│    distinct candidate profile baselines.                                                         │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 4. DEEP CODE EVIDENCE TRIGGER                                                                    │
│    Candidate wants their public GitHub repository and SQL capstone scripts directly parsed to   │
│    prove skills that are difficult to articulate on a 1-page resume.                             │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Commercial Validation Experiments

To validate monetization hypotheses without making unsupported claims, the following commercial experiments are integrated into the product plan:

### EXP-BIZ-01: Willingness-to-Pay & Pricing Elasticity Test `[HYPOTHESIS]`
* **Hypothesis:** Early-career job seekers actively interviewing will convert to Premium Copilot Pro at $\$15/\text{month}$ with a conversion rate $\ge 4.0\%$ from weekly active free users `[PLANNING ASSUMPTION]`.
* **Method:** Test three pricing variants on active candidates reaching their 15-snapshot storage limit:
  * Variant A: $\$9/\text{month}$
  * Variant B: $\$15/\text{month}$ (Baseline hypothesis)
  * Variant C: $\$24/\text{month}$ (or $\$49$ one-time 4-month Season Pass)
* **Primary Metric:** Free-to-Paid Conversion Rate, Revenue per Active User (ARPU).
* **Guardrail:** Drop-off rate at paywall; net promoter score (NPS) must not decline.
* **Decision Rule:** Select price point maximizing Lifetime Value ($LTV = ARPU \times \text{Average Search Months}$).

### EXP-BIZ-02: Feature Value Attribution Audit `[HYPOTHESIS]`
* **Hypothesis:** Advanced interview preparation context (STAR answer generator) drives higher upgrade conversion than raw storage capacity limits.
* **Method:** Measure relative click-through and conversion intent across distinct upgrade banner contexts.
* **Primary Metric:** Upgrade Intent Conversion by Feature Entry Point.
* **Decision Rule:** If interview prep drives $>60\%$ of upgrades, reallocate post-MVP engineering resources to deepen interview simulation tools.
