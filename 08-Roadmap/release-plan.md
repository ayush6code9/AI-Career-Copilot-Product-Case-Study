# Product Release Plan

## Overview

The **Product Release Plan** defines the staged rollout strategy for AI Career Copilot across four progressive release tiers:

1. **Release 0:** Internal Interactive Prototype (Proof of Concept)
2. **Release 1:** Minimum Viable Product Pilot (Core Decision Support Loop)
3. **Release 2:** Reliability & Workflow Release (General Availability Beta)
4. **Release 3:** Intelligence & Expansion Release (Post-MVP Scale Horizon)

To maintain rigorous anti-fabrication standards, this plan specifies **functional scope, validation entry/exit criteria, rollback triggers, and decision owners** without asserting fabricated calendar dates, fictional sprint schedules, or synthetic adoption milestones.

---

## 1. Staged Release Matrix

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                    STAGED RELEASE PROGRESSION                                    │
│                                                                                                  │
│   RELEASE 0: Internal Interactive Prototype                                                      │
│   Scope: Clickable Mockup & Static Parsing Test                                                  │
│   Exit: Usability validation of fit tiers & citation sidebars (Stage 2)                          │
│        ↓                                                                                         │
│   RELEASE 1: MVP Core Decision Pilot                                                             │
│   Scope: Increments 1, 2, 3 (Profile + Raw JD + Fit Analysis + Queue + Snapshot)                 │
│   Exit: EXP-01, EXP-02, AI Grounding < 1.0% Hallucination (Stage 3 & 4)                         │
│        ↓                                                                                         │
│   RELEASE 2: Reliability & Workflow Release                                                      │
│   Scope: Increment 4 (URL Fallback + Warning Banners + Interview Context Drawer + Filters)       │
│   Exit: EXP-03, EXP-04, EXP-05 End-to-End Workflow Benchmark (Stage 5)                         │
│        ↓                                                                                         │
│   RELEASE 3: Intelligence & Expansion Release (Post-MVP)                                         │
│   Scope: P1/P2 Capabilities (Browser Extension + Repo Ingestion + Stagnation Alerts)             │
│   Exit: Sustained North Star (W-HCCD) Growth & Retention > 40%                                   │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Detailed Release Specifications

### Release 0 — Internal Interactive Prototype (Proof of Concept)

* **Status:** `[PLANNED / PROPOSED]`
* **Strategic Objective:** Prove the core visual hierarchy, interaction mental model, and cognitive comprehension of qualitative fit tiers and citation sidebars before investing in complete backend infrastructure.
* **Target Audience:** Internal product team, design reviewers, and 8–10 moderated user research participants `[DESIGN TARGET]`.
* **Included Capabilities:**
  * Interactive click-through prototype of 5 qualitative fit tiers.
  * Side-by-side evidence inspection drawer with mocked candidate quotes.
  * 4-category requirement breakdown visualization.
* **Excluded Capabilities:**
  * Live LLM API execution, persistent database storage, live URL scraping, full resume PDF extraction.
* **Validation Requirement & Success Criteria:**
  * 100% of participants correctly distinguish a *Hard Prerequisite* from a *Learnable on Job* tool in think-aloud testing `[DESIGN TARGET]`.
  * Qualitative tier comprehension score $\ge 4.5 / 5.0$ Likert `[DESIGN TARGET]`.
* **Rollback / Pivot Condition:** If participants report confusion over qualitative tiers or demand numerical scores, redesign UI hierarchy prior to Release 1.
* **Decision Owner:** Lead Product Designer & Product Manager.

---

### Release 1 — MVP Core Decision Pilot (Closed Alpha Cohort)

* **Status:** `[PLANNED / VALIDATION DEPENDENT]`
* **Strategic Objective:** Validate the foundational end-to-end decision-support loop under real candidate search conditions.
* **Target Audience:** Closed pilot cohort of 30–50 final-year STEM / Business Analyst students actively applying for entry-level roles `[DESIGN TARGET]`.
* **Included Capabilities (Increments 1–3):**
  * `CAP-01`, `CAP-02`: Resume PDF parsing and manual candidate profile editor.
  * `CAP-04`, `CAP-05`: Raw JD text ingestion box and 4-category taxonomy structuring.
  * `CAP-06`, `CAP-07`, `CAP-08`, `CAP-09`, `CAP-11`: Demonstrated matches, overlaps, gap severity, qualitative fit tiers, and insufficient-info handling.
  * `CAP-10`, `CAP-12`, `CAP-13`, `CAP-14`: Candidate override, 3-tier opportunity queue, immutable JD snapshot, and Kanban tracking.
* **Excluded Capabilities:**
  * Live web URL scraping, interview prep drawer, resume framing cues, browser extensions.
* **Validation Requirement & Success Criteria:**
  * **EXP-01 Passed:** Qualitative tiers achieve higher decision confidence than baseline numerical scores.
  * **EXP-02 Passed:** Evidence inspection rate $\ge 60\%$.
  * **AI Grounding Launch Gate Passed:** Unsupported Evidence (Hallucination) Rate strictly $< 1.0\%$.
  * Weekly High-Confidence Career Decisions (W-HCCD) $\ge 3.0$ per active candidate `[DESIGN TARGET]`.
* **Rollback / Kill-Switch Condition:** If Unsupported Evidence Rate $\ge 1.0\%$ or JD ingestion failure rate $\ge 5.0\%$, immediately pause new candidate intake and enter diagnostic remediation.
* **Decision Owner:** Product Manager & AI Engineering Lead.

---

### Release 2 — Reliability & Workflow Release (General Availability Beta)

* **Status:** `[PLANNED / VALIDATION DEPENDENT]`
* **Strategic Objective:** Remove operational friction, enhance interview context support, and scale the user base to broad public access.
* **Target Audience:** Open public beta across target universities and early-career communities.
* **Included Capabilities (Increment 4 Polish):**
  * `CAP-03`: Direct URL ingestion with transparent raw text fallback.
  * `CAP-15`: Incomplete JD and ambiguity warning banners.
  * `CAP-16`: Interview preparation context drawer with talking points.
  * `CAP-17`: Resume framing guidance for demonstrated project matches.
  * `CAP-18`: Target role filters and multi-dimensional search.
* **Excluded Capabilities:**
  * External third-party ATS integrations, automated code repository parsers.
* **Validation Requirement & Success Criteria:**
  * **EXP-03 Passed:** Direct URL parser failure rate $< 15\%$ on standard ATS boards.
  * **EXP-05 Passed:** End-to-end workflow benchmark demonstrates $\ge 30\%$ decision time reduction vs. status quo without decision degradation.
  * 7-Day Triage Return Rate $\ge 35\%$ `[DESIGN TARGET]`.
* **Rollback Condition:** If URL parser failure rate $> 25\%$, revert UI to promote Raw JD Paste as the default primary tab.
* **Decision Owner:** Product Manager & Technical Lead.

---

### Release 3 — Intelligence & Expansion Release (Post-MVP Horizon)

* **Status:** `[FUTURE / POST-MVP]`
* **Strategic Objective:** Expand candidate profile depth, support multi-track searches, and provide proactive market intelligence.
* **Target Audience:** Scaled user base across technical, analytical, and adjacent early-career domains.
* **Included Capabilities (P1 / P2 Horizon):**
  * Lightweight browser extension for 1-click JD capture on job boards.
  * Deep GitHub repository and code artifact parsing for verified technical evidence.
  * Multi-version resume linking across distinct role tracks (e.g., Data Engineering vs. Data Analyst).
  * Automated job stagnation and follow-up reminders.
* **Excluded Capabilities (Permanent Non-Goals):**
  * Auto-apply spam bots, ungrounded resume writers, cold recruiter spam engines.
* **Validation Requirement & Success Criteria:**
  * Sustained North Star Metric (W-HCCD) expansion across cohorts.
  * 30-Day Decision Retention Rate $\ge 25\%$ `[DESIGN TARGET]`.
* **Rollback Condition:** Deprecate any advanced intelligence module that increases candidate cognitive confusion or unsupported AI claims.
* **Decision Owner:** VP of Product & Engineering Director.
