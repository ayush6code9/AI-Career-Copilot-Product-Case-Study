# Product Goals & Strategic Outcomes

This document establishes the strategic goals, directional success criteria, and explicit non-goals for **AI Career Copilot**.

---

## 1. Strategic Outcome (The Strategic North Star Direction)

> **Strategic Direction**:  
> **"Maximize the proportion of candidate job-search effort invested in genuinely relevant, high-conviction opportunities, while minimizing wasted hours on ambiguous, low-probability listings."**

```
                     IDEAL USER VALUE CONVERSION LOOP
┌───────────────────────┐       ┌───────────────────────┐       ┌───────────────────────┐
│ Rapid Fit Evaluation  │ ───▶  │ High-Conviction       │ ───▶  │ Higher Interview      │
│ & Gap Clarity         │       │ Targeted Applications │       │ Readiness & Conversion│
└───────────────────────┘       └───────────────────────┘       └───────────────────────┘
```

### What Success Looks Like:
* Candidates feel in complete control of their job pipeline, knowing exactly why they applied to each role and how their projects map to requirements `[ASSUMPTION]`.
* Candidate time spent per evaluation drops from 30+ minutes of manual tab confusion to <3 minutes of structured review `[HYPOTHESIS]`.
* Complete elimination of context loss when recruiters reach out for initial screening interviews `[ASSUMPTION]`.

### User Behaviors That Indicate High Value:
* **Active Prioritization**: Candidate regularly triages parsed roles and selects high-fit targets to apply for `[PRODUCT INFERENCE]`.
* **Deep Explainability Consumption**: Candidate expands and reads match reasoning and gap breakdowns before moving a role to "Applied" `[PRODUCT INFERENCE]`.
* **Pipeline Progression**: Candidate updates application status across stages (Applied ➔ Screening ➔ Interview) within the integrated tracker `[PRODUCT INFERENCE]`.

### User Behaviors That Should NOT Be Optimized:
* **Raw Application Volume Maximization**: We do *not* incentivize blasting 100+ applications per day `[PRODUCT INFERENCE]`.
* **Passive Job Board Doom-Scrolling**: We do *not* optimize for hours spent browsing endless unranked listings `[PRODUCT INFERENCE]`.

---

## 2. Structured Goal Hierarchy

### A. User Goals
* **UG-01: Rapid JD Decoding**: Enable candidates to comprehend the true technical prerequisites of an entry-level posting in under 2 minutes `[PRODUCT INFERENCE]`.
  * *Addresses*: `PP-03` (Vague & Bloated Requirement Stacks).
  * *Eventual Measurement Direction*: Time spent reviewing JD before taking a decision action.
* **UG-02: Transparent Qualification Confidence**: Give candidates objective, evidence-backed confidence regarding whether their projects meet role criteria `[ASSUMPTION]`.
  * *Addresses*: `PP-05` (Opaque Fit Badges) & `PP-06` (Unclear Gaps).
  * *Eventual Measurement Direction*: Candidate qualitative confidence ratings and fit breakdown interaction rates.
* **UG-03: Zero Context Loss**: Provide instant retrieval of evaluated JD snapshots and match notes during recruiter outreach `[FACT]`.
  * *Addresses*: `PP-09` (Pipeline Disorganization & Expired URLs).
  * *Eventual Measurement Direction*: Rate of accessing saved job records from tracker during interview stages.

### B. Product Goals
* **PG-01: High-Fidelity Fit Extraction**: Accurately decompose JDs into Core Prerequisites vs. Preferred Tools across target technical disciplines (Data, AI/ML, Software, Product Analytics) `[PRODUCT INFERENCE]`.
  * *Addresses*: `PP-02` (Misleading Entry-Level Labels) & `PP-03` (Bloated JDs).
  * *Eventual Measurement Direction*: Fit explanation accuracy and user feedback sentiment (e.g., "Was this breakdown helpful?").
* **PG-02: High-Conviction Triage**: Successfully rank and group opportunities into actionable priority tiers (High Fit, Stretch, Low Conviction) `[PRODUCT INFERENCE]`.
  * *Addresses*: `PP-07` (Bandwidth Dilution & Decision Paralysis).
  * *Eventual Measurement Direction*: Proportion of applications submitted to High Fit vs. Low Conviction tiers.
* **PG-03: Seamless Workflow Integration**: Consolidate discovery ingestion, fit analysis, and status tracking into a single continuous interface `[PRODUCT INFERENCE]`.
  * *Addresses*: `PP-01` (Fragmentation) & `PP-09` (Disorganized Spreadsheets).
  * *Eventual Measurement Direction*: Ratio of analyzed jobs saved directly to the tracking pipeline.

### C. Business Goals (Early Stage)
* **BG-01: High Candidate Retention & Workflow Stickiness**: Become the candidate's primary daily dashboard throughout their active job hunt lifecycle `[PRODUCT INFERENCE]`.
  * *Eventual Measurement Direction*: Weekly active usage and repeat session frequency during active search.
* **BG-02: Organic Peer-to-Peer Advocacy**: Generate strong organic word-of-mouth referral across college senior cohorts and early-career communities `[ASSUMPTION]`.
  * *Eventual Measurement Direction*: Organic sign-up attribution and referral velocity.

---

## 3. Explicit Non-Goals

| Non-Goal | Rationale for Exclusion |
| :--- | :--- |
| **NG-01: Auto-Submitting Applications** | We deliberately do not build automated form-submission bots that blast employer portals. This protects candidate brand and prevents ecosystem spam `[PRODUCT INFERENCE]`. |
| **NG-02: Comprehensive LMS / Course Platform** | We do not build an in-house online academy to teach full coding courses; we identify gaps and recommend targeted learning directions `[PRODUCT INFERENCE]`. |
| **NG-03: Employer-Facing Recruitment ATS** | We do not sell candidate resume databases to recruiters or optimize for enterprise hiring screens in Phase 1/2. We remain 100% candidate-aligned `[PRODUCT INFERENCE]`. |
| **NG-04: Non-Technical Role Coverage** | We do not attempt to support subjective non-technical roles (e.g., Creative Design, Sales) in early product stages `[PRODUCT INFERENCE]`. |
