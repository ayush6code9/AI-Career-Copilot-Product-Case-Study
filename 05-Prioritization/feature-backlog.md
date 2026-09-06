# Feature Backlog & Prioritization Scoring

This document details the prioritized product backlog across the 5 core modules of **AI Career Copilot**, evaluating each capability through the Dependency-Aware Value-Risk Framework (DAVR).

---

## 1. Comprehensive Feature Backlog Table

| Feature ID | Capability & Scope | User Problem Addressed | JTBD Alignment | User Value (1-5) | Relative Effort (1-5) | Technical Risk | Direct Dependency | Priority Tier |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: | :--- | :---: |
| **FB-CP-01** | **Resume PDF Parsing & Entity Extraction** | `PP-08` (Form fatigue during onboarding) | `JTBD 1` | 4 | 3 | Med | None | **P0 (Must)** |
| **FB-CP-02** | **Manual Profile & Project Evidence Editor** | `PP-04` (Unverified / misparsed candidate data) | `JTBD 1` | 4 | 2 | Low | FB-CP-01 | **P0 (Must)** |
| **FB-CP-03** | **Target Role & Preference Calibration** | `PP-01` (Unfiltered irrelevant roles) | `JTBD 2` | 3 | 1 | Low | None | **P1 (Should)**|
| **FB-CP-04** | **GitHub / Live Project URL Linking** | `PP-04` (Lack of proof for non-traditional devs) | `JTBD 4` | 3 | 2 | Low | FB-CP-02 | **P2 (Defer)** |
| **FB-JD-01** | **Raw Job Description Text Ingestion** | `PP-01` (Fragmentation across job boards) | `JTBD 1` | 5 | 1 | Low | None | **P0 (Must)** |
| **FB-JD-02** | **Live Job Posting URL Extraction** | `PP-01` (Copy-paste tab friction) | `JTBD 1` | 4 | 4 | High | FB-JD-01 | **P1 (Should)**|
| **FB-JD-03** | **Auto-Detection of Title/Company/Location** | `PP-09` (Manual metadata entry overhead) | `JTBD 5` | 3 | 2 | Med | FB-JD-01 | **P0 (Must)** |
| **FB-PS-01** | **Requirement Entity Structuring (Hard vs Preferred)** | `PP-03` (Bloated, unstandardized JDs) | `JTBD 1` | 5 | 3 | Med | FB-JD-01 | **P0 (Must)** |
| **FB-PS-02** | **Ambiguity & Low-Signal JD Warning Alert** | `PP-03` (Fluff-heavy, uncalibrated JDs) | `JTBD 1` | 4 | 2 | Low | FB-PS-01 | **P1 (Should)**|
| **FB-FA-01** | **Multi-Dimensional Fit Alignment Engine** | `PP-05` (Opaque black-box match scores) | `JTBD 1` | 5 | 3 | Med | FB-CP-02, FB-PS-01 | **P0 (Must)** |
| **FB-FA-02** | **Qualitative Fit Tiers (5 Tiers; No % Score)** | `PP-05` (Pseudo-precision and false anxiety) | `JTBD 1` | 5 | 2 | Low | FB-FA-01 | **P0 (Must)** |
| **FB-FA-03** | **Grounded Evidence Tooltips & Citations** | `PP-05` (Skepticism of AI hallucinations) | `JTBD 1` | 5 | 2 | Med | FB-FA-01 | **P0 (Must)** |
| **FB-FA-04** | **Categorized Gap Severity Tiers (4 Tiers)** | `PP-06` (Unclear gaps causing drop-off) | `JTBD 3` | 5 | 2 | Low | FB-FA-01 | **P0 (Must)** |
| **FB-FA-05** | **Actionable Recommendation & Prep Cues** | `PP-08` (Generic, untailored submissions) | `JTBD 4` | 4 | 2 | Low | FB-FA-01 | **P1 (Should)**|
| **FB-PR-01** | **3-Tier Opportunity Prioritization Queue** | `PP-07` (30-tab paralysis and time dilution) | `JTBD 2` | 5 | 2 | Low | FB-FA-02 | **P0 (Must)** |
| **FB-PR-02** | **Manual Priority Override & Tier Dragging** | `PP-07` (Loss of candidate personal agency) | `JTBD 2` | 3 | 1 | Low | FB-PR-01 | **P1 (Should)**|
| **FB-PR-03** | **Queue Role Filters & Urgency Sorting** | `PP-07` (Disorganized search sprint) | `JTBD 2` | 3 | 1 | Low | FB-PR-01 | **P2 (Defer)** |
| **FB-TR-01** | **Immutable Local Job Snapshot Archival** | `PP-09` (Context loss from expired 404 links)| `JTBD 5` | 5 | 2 | Low | FB-FA-01 | **P0 (Must)** |
| **FB-TR-02** | **Interactive 7-State Kanban Pipeline Board** | `PP-09` (Spreadsheet maintenance friction) | `JTBD 5` | 4 | 2 | Low | FB-TR-01 | **P0 (Must)** |
| **FB-TR-03** | **Interview Preparation Context Slide-Out Drawer** | `PP-09` (Unprepared for recruiter calls) | `JTBD 5` | 4 | 2 | Low | FB-TR-01 | **P1 (Should)**|
| **FB-TR-04** | **Rejection & Funnel Analysis Logging** | `PP-09` (Lack of visibility into drop-offs) | `JTBD 6` | 2 | 2 | Low | FB-TR-02 | **P2 (Defer)** |
| **FB-NO-01** | **Automated ATS Application Submission Bot** | *N/A (Candidate spam)* | *None* | Negative | 5 | Critical | None | **P3 (Reject)** |
| **FB-NO-02** | **Generic Resume Hallucination Generator** | *N/A (Inauthentic credentials)* | *None* | Negative | 4 | High | None | **P3 (Reject)** |

---

## 2. Quantitative & Qualitative Scoring Breakdown

```
DAVR Priority Score = (User Impact × JTBD Multiplier × Confidence) ÷ Relative Effort
```

| Feature ID | Capability | Impact (1-5) | JTBD Multiplier | Confidence (0.5-1.0) | Effort (1-5) | DAVR Score | Priority |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **FB-JD-01** | Raw JD Text Ingestion | 5 | 1.5 | 1.0 | 1 | **7.50** | **P0** |
| **FB-FA-02** | Qualitative Fit Tiers | 5 | 1.5 | 0.9 | 2 | **3.38** | **P0** |
| **FB-FA-04** | Categorized Gap Severity | 5 | 1.5 | 0.9 | 2 | **3.38** | **P0** |
| **FB-FA-03** | Grounded Evidence Citations | 5 | 1.5 | 0.9 | 2 | **3.38** | **P0** |
| **FB-TR-01** | Immutable Snapshot Archival | 5 | 1.2 | 1.0 | 2 | **3.00** | **P0** |
| **FB-PR-01** | 3-Tier Prioritization Queue | 5 | 1.5 | 0.8 | 2 | **3.00** | **P0** |
| **FB-CP-02** | Manual Profile Editor | 4 | 1.2 | 1.0 | 2 | **2.40** | **P0** |
| **FB-FA-01** | Multi-Dimensional Fit Engine | 5 | 1.5 | 0.8 | 3 | **2.00** | **P0** |
| **FB-TR-02** | Kanban Tracking Board | 4 | 1.2 | 0.8 | 2 | **1.92** | **P0** |
| **FB-PS-01** | Requirement Structuring | 5 | 1.2 | 0.8 | 3 | **1.60** | **P0** |
| **FB-CP-01** | Resume PDF Parsing | 4 | 1.2 | 0.8 | 3 | **1.28** | **P0** |
| **FB-FA-05** | Actionable Recommendation Cues | 4 | 1.2 | 0.8 | 2 | **1.92** | **P1** |
| **FB-PS-02** | Ambiguity Warning Alerts | 4 | 1.2 | 0.8 | 2 | **1.92** | **P1** |
| **FB-TR-03** | Interview Context Drawer | 4 | 1.2 | 0.8 | 2 | **1.92** | **P1** |
| **FB-JD-02** | Live Job URL Extraction | 4 | 1.2 | 0.8 | 4 | **0.96** | **P1** |
| **FB-CP-03** | Target Role Preferences | 3 | 1.0 | 0.9 | 1 | **2.70** | **P1** |
| **FB-PR-02** | Priority Tier Override | 3 | 1.2 | 0.8 | 1 | **2.88** | **P1** |
| **FB-CP-04** | GitHub URL Metadata Linking | 3 | 1.0 | 0.8 | 2 | **1.20** | **P2** |
| **FB-PR-03** | Queue Filtering / Sorting | 3 | 1.0 | 0.8 | 1 | **2.40** | **P2** |
| **FB-TR-04** | Funnel Analysis & Rejection Log | 2 | 1.0 | 0.8 | 2 | **0.80** | **P2** |

---

## 3. Constrained MVP Scenario (Limited Engineering Capacity)

> **Hypothetical Scenario**: Assume engineering capacity is restricted to a tight 2-developer sprint `[HYPOTHETICAL]`. What is the smallest viable product that proves whether explainable job-fit analysis solves candidate decision paralysis?

```
┌────────────────────────────────────────────────────────────────────────┐
│                        MVP CONSTRAINED BOUNDARY                        │
├────────────────────────────────────────────────────────────────────────┤
│ MUST BUILD (Core Value Loop):                                          │
│ • FB-CP-01/02: Lightweight Resume Parsing & Manual Skill Verification  │
│ • FB-JD-01: Raw Text JD Paste (100% reliable, zero scraping fragility) │
│ • FB-PS-01: Structuring Hard vs. Preferred Requirements                │
│ • FB-FA-01/02/03/04: Explainable Fit Engine + Evidence + Gap Severity   │
│ • FB-PR-01: 3-Tier Opportunity Triage Queue                            │
│ • FB-TR-01/02: Immutable Snapshot Archival & Basic Kanban Pipeline    │
├────────────────────────────────────────────────────────────────────────┤
│ SHOULD BUILD (High-ROI Fast Follows):                                  │
│ • FB-JD-02: URL Ingestion with fallback                                │
│ • FB-TR-03: Interview Cheat Sheet Drawer                               │
│ • FB-PS-02: Ambiguity Warnings                                         │
├────────────────────────────────────────────────────────────────────────┤
│ DEFER TO POST-MVP (P2):                                                │
│ • FB-CP-04: GitHub Live Repo Parsing                                   │
│ • FB-TR-04: Funnel Rejection Metrics                                   │
├────────────────────────────────────────────────────────────────────────┤
│ EXPLICITLY REJECT (P3 Non-Goals):                                      │
│ • FB-NO-01: Auto-submission spam bots                                  │
│ • FB-NO-02: Hallucinatory resume rewriters                             │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 4. "If We Could Only Build 3 Things" (The Extreme MVP)

If engineering constraints forced the team to build strictly **three capabilities**, the selection would be:

```
┌────────────────────────────────────────────────────────────────────────┐
│                      THE 3-CAPABILITY EXTREME MVP                      │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Verified Candidate Profile Baseline (FB-CP-01 / FB-CP-02)           │
│ 2. Explainable Fit Analysis & Evidence Citations (FB-FA-01 / 02 / 03)  │
│ 3. Immutable Snapshot Archival & Pipeline Tracker (FB-TR-01 / FB-TR-02)│
└────────────────────────────────────────────────────────────────────────┘
```

### Capability 1: Verified Candidate Profile Baseline (FB-CP-01 / FB-CP-02)
* **Why Essential**: Without a structured, candidate-verified baseline of technical skills, capstone projects, and coursework, AI qualification comparison is impossible `[FACT]`.
* **User Pain Addressed**: `PP-08` (Onboarding form fatigue) & `PP-04` (Unverified data).
* **JTBD Supported**: `JTBD 1` (Establishes candidate evidence anchor).
* **Product Learning Generated**: Tests whether users prefer 1-click resume parsing vs. manual skill input.
* **Capabilities Sacrificed**: Sacrifices automated GitHub repo scraping and detailed career goal surveys.

### Capability 2: Explainable Job-Fit Analysis with Grounded Evidence (FB-FA-01 / 02 / 03 / 04)
* **Why Essential**: Represents the core value engine and primary differentiator of the product. Eliminates the cognitive burden of manually decoding ambiguous 15-skill job descriptions `[PRODUCT INFERENCE]`.
* **User Pain Addressed**: `PP-03` (Bloated JDs), `PP-05` (Opaque badges), and `PP-06` (Unclear gaps).
* **JTBD Supported**: `JTBD 1` (Primary Core Job).
* **Product Learning Generated**: Validates whether qualitative tiers (Strong/Stretch/Low) and evidence tooltips give candidates sufficient conviction to make application decisions.
* **Capabilities Sacrificed**: Sacrifices numerical fit algorithms, resume tailoring suggestions, and automated mock interview prep.

### Capability 3: Immutable Snapshot Archival & Pipeline Tracker (FB-TR-01 / FB-TR-02)
* **Why Essential**: Solves the severe post-application problem where job links break after closing, leaving candidates blind when recruiters reach out weeks later `[FACT]`.
* **User Pain Addressed**: `PP-09` (Context loss & spreadsheet abandonment).
* **JTBD Supported**: `JTBD 5` (Centralized Application Intelligence).
* **Product Learning Generated**: Measures whether candidate retention is driven by active pipeline management or single-session fit evaluations.
* **Capabilities Sacrificed**: Sacrifices automated calendar syncing, email webhook ingestion, and complex funnel analytics.
