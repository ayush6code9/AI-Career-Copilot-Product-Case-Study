# MVP Release Roadmap (Execution Increments)

## Overview

The **MVP Release Roadmap** organizes the delivery of the approved Minimum Viable Product (defined in [04-PRD/prd.md](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/04-PRD/prd.md) and [05-Prioritization/feature-backlog.md](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/feature-backlog.md)) into **four logical execution increments**.

Each increment represents a coherent, independently testable milestone that unlocks critical system capabilities while enforcing strict validation gates before subsequent development begins.

---

## 1. Incremental Execution Breakdown

```
┌───────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   MVP ROADMAP CRITICAL PATH                                       │
│                                                                                                   │
│  INCREMENT 1: FOUNDATION                                                                          │
│  [Resume PDF + Manual Profile] ──▶ [Raw JD Ingestion + 4-Category Taxonomy]                       │
│                                                                                                   │
│  INCREMENT 2: CORE INTELLIGENCE                                                                   │
│  [Demonstrated Matches + Gaps + 5 Fit Tiers + Verifiable Citations]                               │
│                                                                                                   │
│  INCREMENT 3: DECISION & TRACKING                                                                 │
│  [3-Tier Opportunity Queue + Immutable JD Snapshot + Kanban Tracking + Override]                │
│                                                                                                   │
│  INCREMENT 4: TRUST & OPERATIONAL POLISH                                                          │
│  [URL Ingestion Fallback + Ambiguity Warnings + Interview Context Drawer + Role Filters]         │
└───────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

### Increment 1 — Foundation (Candidate Profile & Job Description Normalization)

* **Product Goal:** Establish reliable, structured inputs on both sides of the evaluation equation (Candidate Evidence and Role Requirements).
* **Core Problem Addressed:** Candidates lack a structured repository of their verified skills, and job descriptions are chaotic, unformatted walls of text.
* **Capabilities Delivered:**
  1. `CAP-01`: Structured Candidate Profile & Evidence Extraction (Resume PDF upload + structured parsing).
  2. `CAP-02`: Manual Profile Item Verification & Project Evidence Editor.
  3. `CAP-04`: Direct Raw JD Text Ingestion (Paste box with auto-formatting and metadata extraction).
  4. `CAP-05`: 4-Category Requirement Taxonomy Structuring (*Hard Prerequisite*, *Core Competency*, *Preferred Tool*, *Domain Context*).
* **Technical & Data Dependencies:** None (Entry point of the architecture).
* **Validation Gate:**
  * Candidate Profile Creation Completion Rate $\ge 80\%$ `[DESIGN TARGET]`.
  * Requirement Structuring Extraction Precision $\ge 90\%$ `[DESIGN TARGET]`.
* **Exit Signal:** Users can reliably parse a resume, edit missing projects, and ingest raw job descriptions into 4 distinct requirement categories without data loss.

---

### Increment 2 — Core Intelligence (Explainable Job-Fit Analysis Engine)

* **Product Goal:** Provide transparent, grounded, and explainable evaluation comparing candidate evidence directly against structured JD requirements.
* **Core Problem Addressed:** Black-box percentage scores create false confidence or irrational rejection; candidates cannot determine *why* they do or do not fit a role.
* **Capabilities Delivered:**
  1. `CAP-06`: Demonstrated Match Mapping with Exact Candidate Quote Citations.
  2. `CAP-07`: Transferable Capability & Adjacent Skill Overlap Identification.
  3. `CAP-08`: 4-Level Skill Gap Classification (*Blocking*, *Important*, *Learnable on Job*, *Nice-to-Have*).
  4. `CAP-09`: 5-Tier Qualitative Fit Recommendation Engine (*Strong Fit*, *Reasonable Fit*, *Stretch*, *Low Fit*, *Insufficient Information*).
  5. `CAP-11`: Insufficient-Information Handling & Explicit Ambiguity Flagging.
* **Technical & Data Dependencies:** Requires completed Increment 1 (Structured Profile + Structured JD).
* **Validation Gate:**
  * **EXP-01 (Qualitative Tiers vs. Score):** Decision usefulness/confidence $\ge 4/5$ Likert `[VALIDATION REQUIRED]`.
  * **EXP-02 (Evidence Citations):** Evidence inspection rate $\ge 60\%$, correction engagement $\ge 15\%$ `[VALIDATION REQUIRED]`.
  * **Safety Kill-Switch:** Unsupported Evidence (Hallucination) Rate $<1.0\%$ `[VALIDATION REQUIRED]`.
* **Exit Signal:** Candidates review fit analyses, inspect citations, understand gap severity, and can articulate why a job fits their background.

---

### Increment 3 — Decision & Tracking (Actionable Workflow & Persistent Archive)

* **Product Goal:** Transform standalone evaluation into a coherent opportunity triage workflow with persistent, reliable tracking.
* **Core Problem Addressed:** Job evaluation happens in fragmented tabs; candidates lose context, and job postings disappear (404) during interview stages.
* **Capabilities Delivered:**
  1. `CAP-12`: 3-Tier Opportunity Triage Queue (*High Priority / Apply Now*, *Targeted Upskill*, *Archive / Low Priority*).
  2. `CAP-13`: Immutable Local JD Text Snapshot & Requirements Archive.
  3. `CAP-14`: Lightweight Kanban Application Tracking (*Bookmarked*, *Drafting*, *Applied*, *Interviewing*, *Offer*, *Rejected*).
  4. `CAP-10`: Candidate Agency & Fit Tier Manual Override Mechanism.
* **Technical & Data Dependencies:** Requires completed Increment 2 (Fit Analysis Engine).
* **Validation Gate:**
  * **EXP-04 (Auto-Queue vs. Manual):** Time-to-Prioritization reduction with override rate between $10\text{--}30\%$ (confirming active agency without friction) `[VALIDATION REQUIRED]`.
  * **Workflow Retention:** 7-Day Return Triage Rate $\ge 35\%$ `[DESIGN TARGET]`.
* **Exit Signal:** Candidates seamlessly transition from reviewing fit analysis to sorting roles into queues, logging application stages, and referencing stored JD snapshots during interviews.

---

### Increment 4 — Trust & Operational Polish (Friction Reduction & Workflow Depth)

* **Product Goal:** Remove input friction, provide contextual interview preparation data, and ensure complete user agency.
* **Core Problem Addressed:** Copy-pasting long text can feel repetitive, and candidates struggle to formulate interview talking points from raw gap analyses.
* **Capabilities Delivered:**
  1. `CAP-03`: URL-Based JD Ingestion with Transparent Raw Text Fallback.
  2. `CAP-15`: Ambiguity & Incomplete JD Warning Banners.
  3. `CAP-16`: Interview Preparation Context Drawer (Grounding summary & talking points).
  4. `CAP-17`: Resume Bullet Narrative Framing Cues (Contextual guidance based on demonstrated strengths).
  5. `CAP-18`: Target Role Filter & Search Dimension Toggles.
* **Technical & Data Dependencies:** Requires completed Increments 1–3.
* **Validation Gate:**
  * **EXP-03 (Raw Paste vs. URL Ingestion):** Fallback activation $<15\%$ on standard ATS pages; overall ingestion success $>95\%$ `[VALIDATION REQUIRED]`.
  * **EXP-05 (End-to-End Benchmark):** Time-to-High-Confidence Decision reduced by $\ge 30\%$ vs. status quo without degrading decision accuracy `[VALIDATION REQUIRED]`.
* **Exit Signal:** The complete closed-loop product is operating with high ingestion reliability, active candidate trust, and robust interview context support.

---

## 2. Master MVP Roadmap Table

The following table summarizes all 18 MVP capabilities across the four execution increments:

| Increment | Product Goal | Capability ID & Name | Core Dependencies | Validation Gate / Experiment | Phase 6 Primary Metric | Roadmap Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Inc 1** | Candidate Foundation | `CAP-01`: Resume PDF Parser & Profile | None | Prototype Usability (Stage 2) | Profile Creation Rate | `[PLANNED]` |
| **Inc 1** | Candidate Foundation | `CAP-02`: Manual Profile & Project Editor | `CAP-01` | Profile Verification Rate | Profile Edit Completion % | `[PLANNED]` |
| **Inc 1** | JD Normalization | `CAP-04`: Raw Text JD Ingestion Box | None | Prototype Usability (Stage 2) | Ingestion Success Rate | `[PLANNED]` |
| **Inc 1** | JD Normalization | `CAP-05`: 4-Category Taxonomy Extractor | `CAP-04` | Extraction Precision Audit | Taxonomy Accuracy % | `[PLANNED]` |
| **Inc 2** | Fit Intelligence | `CAP-06`: Demonstrated Match Mapping | `CAP-01`, `CAP-05` | EXP-02 (Evidence Citations) | Evidence Inspection Rate | `[PLANNED]` |
| **Inc 2** | Fit Intelligence | `CAP-07`: Transferable Overlap Mapping | `CAP-01`, `CAP-05` | Qualitative Review (Stage 2) | Overlap Identification % | `[PLANNED]` |
| **Inc 2** | Fit Intelligence | `CAP-08`: 4-Level Gap Severity Engine | `CAP-01`, `CAP-05` | User Comprehension Audit | Gap Severity Clarity | `[PLANNED]` |
| **Inc 2** | Fit Intelligence | `CAP-09`: 5-Tier Qualitative Fit Engine | `CAP-06`, `CAP-08` | EXP-01 (Fit Tiers vs Score) | Decision Confidence Score | `[PLANNED]` |
| **Inc 2** | Fit Intelligence | `CAP-11`: Insufficient-Info Flagging | `CAP-05` | Grounding Audit (Stage 3) | Ambiguity Detection Rate | `[PLANNED]` |
| **Inc 3** | Decision Support | `CAP-10`: Candidate Fit Manual Override | `CAP-09` | EXP-01 / EXP-04 | User Override Frequency | `[PLANNED]` |
| **Inc 3** | Decision Support | `CAP-12`: 3-Tier Opportunity Queue | `CAP-09` | EXP-04 (Auto-Queue) | Time-to-Prioritization | `[PLANNED]` |
| **Inc 3** | Workflow Tracking | `CAP-13`: Immutable Local JD Snapshot | `CAP-04` | Data Persistence Audit | Snapshot Reference Rate | `[PLANNED]` |
| **Inc 3** | Workflow Tracking | `CAP-14`: Lightweight Kanban Tracker | `CAP-12`, `CAP-13` | Workflow Benchmark (Stage 3) | 7-Day Triage Retention | `[PLANNED]` |
| **Inc 4** | Friction Reduction | `CAP-03`: URL Ingestion + Fallback | `CAP-04` | EXP-03 (Ingestion Methods) | Fallback Friction Rate | `[PLANNED]` |
| **Inc 4** | Friction Reduction | `CAP-15`: Incomplete JD Warning Banner | `CAP-11` | User Awareness Audit | Ambiguous Review Time | `[PLANNED]` |
| **Inc 4** | Workflow Depth | `CAP-16`: Interview Prep Context Drawer | `CAP-06`, `CAP-08` | Pilot Feedback (Stage 4) | Drawer Engagement Rate | `[PLANNED]` |
| **Inc 4** | Workflow Depth | `CAP-17`: Resume Framing Guidance | `CAP-06`, `CAP-07` | Pilot Feedback (Stage 4) | Framing Inspection Rate | `[PLANNED]` |
| **Inc 4** | Workflow Depth | `CAP-18`: Target Role Filters & Search | `CAP-14` | Usability Check (Stage 4) | Filter Usage Frequency | `[PLANNED]` |

*Note: All items are strictly designated `[PLANNED]` as future analytical targets; no implementation or production deployment is claimed.*
