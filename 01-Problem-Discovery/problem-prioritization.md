# Problem Prioritization & Scope Boundaries

This document establishes the strategic prioritization of candidate problems to ensure sharp product focus. Problems are evaluated qualitatively using **User Impact**, **Frequency**, **Severity**, **Availability of Alternatives**, and **Product Opportunity**.

---

## 1. Qualitative Problem Evaluation Matrix

| Problem ID | Problem Description | User Impact | Frequency | Severity | Existing Alternatives | Opportunity Attractiveness | Priority Tier |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **PR-01** | **Evaluation & Fit Explainability Deficit** (Candidates cannot determine why a role fits or where real gaps lie) | **High** | **High** | **High** | Poor (Black-box scores or raw LLM copy-paste) | **Critical** | **Primary Focus (P0)** |
| **PR-02** | **Decision Paralysis in Opportunity Prioritization** (Unable to rank which 5–10 roles deserve immediate high-effort attention) | **High** | **High** | **High** | Poor (Arbitrary tab triage or chronological applying) | **Critical** | **Primary Focus (P0)** |
| **PR-03** | **Application Tracking & JD Context Loss** (Expired listings and scattered tracking spreadsheets) | **Medium** | **High** | **Medium** | Moderate (Spreadsheets, Notion, Trello) | **High** | **Primary Focus (P0)** |
| **PR-04** | **Listing Feed Noise & Experience Inflation** (Unfiltered job boards labeling 3-year roles as entry-level) | **Medium** | **High** | **Medium** | Moderate (Keyword filters, niche student boards) | **Medium** | **Secondary (P1)** |
| **PR-05** | **Skill Gap Remediation & Learning Pathways** (Understanding how to upskill for missing requirements) | **Medium** | **Medium** | **Medium** | High (Coursera, YouTube, LeetCode, Documentation) | **Medium** | **Secondary (P1)** |
| **PR-06** | **Repetitive Form-Filling on Employer Portals** (Re-typing resume fields into Workday/Taleo/Greenhouse) | **Medium** | **High** | **Medium** | High (Browser autofill extensions, SimpliApply) | **Low** | **Out of Scope** |
| **PR-07** | **Automated Mass-Application Submission** (Blasting hundreds of applications mechanically) | **Negative** | **High** | **High** | High (Spam bots, mass-apply scrapers) | **Negative Value** | **Out of Scope** |

---

## 2. Problem Categorization & Rationales

### Primary Problem (P0 — Core Product Focus)
> **"Candidates lack transparent, explainable decision-support to evaluate their multi-dimensional fit against ambiguous job descriptions and prioritize where to invest limited application effort."**

* **Why this is Primary**:
  1. It represents the highest cognitive bottleneck in the candidate workflow `[PRODUCT INFERENCE]`.
  2. Incumbent platforms completely fail here: job boards monetize job impressions and employer applicant volume, not candidate decision accuracy `[PRODUCT INFERENCE]`.
  3. Solving fit evaluation unlocks higher application quality, reduced candidate burnout, and focused time allocation `[ASSUMPTION]`.

---

### Secondary Problems (P1 — Near-Term Enablers)
1. **Initial Feed Noise & Experience Tag Filtering**:
   * *Rationale*: Ingesting and filtering job listings is necessary to feed the evaluation engine, but building an exhaustive global job crawler from scratch is commoditized infrastructure. The product should focus on parsing and evaluating ingested roles first.
2. **Actionable Skill Gap Remediation**:
   * *Rationale*: Identifying gaps is part of the core evaluation; prescribing detailed multi-week learning curricula is valuable but secondary to the immediate hiring decision loop.

---

### Out-of-Scope Problems (Deliberately Excluded from Initial Scope)

#### 1. Automated Job Application Submission (Auto-Apply Bots)
* **Decision**: Strictly Excluded.
* **Why this decision?**:
  * Auto-apply bots degrade candidate trust and damage candidate brand with employers `[PRODUCT INFERENCE]`.
  * Flooding recruiters with automated spam increases ATS filter strictness, harming the broader ecosystem `[DESK RESEARCH]`.
  * AI Career Copilot is a **decision-support copilot**, not an automated spam generator. The goal is to maximize decision quality and conversion, not submission volume.

#### 2. Universal ATS Form Autofill
* **Decision**: Excluded from initial phase.
* **Why this decision?**:
  * ATS portals (Workday, Taleo, Greenhouse, Lever) feature highly variable anti-bot mechanisms, captchas, and dynamic form layouts requiring continuous maintenance `[FACT]`.
  * Autofill is an operational convenience, not a strategic decision-support enabler. Candidates can apply directly on official portals once prioritized.

#### 3. Real-Time Recruiter Outreach & Cold Email Messaging
* **Decision**: Excluded from initial phase.
* **Why this decision?**:
  * Generating cold outreach at scale introduces high risk of spamming and privacy compliance overhead `[FACT]`.
  * Diverts focus from candidate evaluation to social outreach automation.

---

## 3. Summary of Strategic Scope Boundary

```
┌────────────────────────────────────────────────────────────────────────┐
│                        IN SCOPE (P0 MVP)                               │
│  ✓ Candidate Profile Baseline (Skills, Projects, Preferences)          │
│  ✓ Explainable Job-Fit Analysis (Matched, Partial, Missing Gaps)       │
│  ✓ Opportunity Prioritization (High Fit, Stretch, Low Conviction)      │
│  ✓ Integrated Application Tracking & Job Snapshot Archival             │
└────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     OUT OF SCOPE (NON-NEGOTIABLE)                      │
│  ✗ Auto-submitting applications to employer portals                    │
│  ✗ Mass email scraping / cold outreach generation                      │
│  ✗ Live ATS browser form autofill bots                                 │
└────────────────────────────────────────────────────────────────────────┘
```
