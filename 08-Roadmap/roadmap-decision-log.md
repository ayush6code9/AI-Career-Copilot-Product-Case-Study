# Roadmap Decision Log

## Overview

This **Roadmap Decision Log** captures the core strategic trade-offs, sequencing logic, and release gating decisions governing the execution of AI Career Copilot.

Each record documents the business context, alternative options evaluated, explicit sacrifices made, and pre-registered revisit triggers, providing interview-defensible proof of disciplined product management.

---

## Decision Records Summary

| ID | Strategic Decision | Core Trade-Off / Focus | Primary Rationale |
| :--- | :--- | :--- | :--- |
| **RD-01** | Fit Analysis Before Discovery | Decision Intelligence vs. Job Search Engine | Deep evaluation is the core differentiator; discovery is already commoditized. |
| **RD-02** | Structured Evidence Before AI | Verifiable Grounding vs. Frictionless Onboarding | Grounding requires verified truth; ungrounded profiles generate hallucinated advice. |
| **RD-03** | Evidence Grounding Release Gate | Trust & Safety vs. Rapid Feature Shipping | Hallucination rate $\ge 1.0\%$ destroys candidate trust and causes interview failure. |
| **RD-04** | Raw JD Ingestion Before URL Scraping | 100% Ingestion Reliability vs. Visual Convenience | Broken scrapers fail the core loop; raw text paste works reliably on any platform. |
| **RD-05** | Prioritization Follows Fit Analysis | Grounded Triage vs. Shallow Keyword Filtering | High-confidence prioritization requires structured match and gap understanding. |
| **RD-06** | Application Tracking in Core MVP | Unified Decision Workspace vs. Isolated Evaluation | Candidates need persistent snapshots and status tracking to complete the workflow. |
| **RD-07** | Validation-Gated Post-MVP Expansion | Hypothesis Validation vs. Fixed Feature Commit | Avoids building complex integrations before proving the core value proposition. |

---

## Detailed Decision Records

### RD-01: Core Fit Analysis Sequenced Before Job Discovery & Aggregation

* **Context:** Early-career candidates find job listings across dozens of disparate sources (LinkedIn, Handshake, Indeed, company portals). We had to choose whether to build a job aggregator first or an evaluation engine.
* **Decision:** Build the deep evaluation and fit analysis engine first (`Increments 1–2`), requiring candidates to bring their own JDs.
* **Alternatives Considered:**
  1. *Build a centralized entry-level job scraper/board first.*
  2. *Integrate third-party job feed APIs.*
* **Rationale:** Job listings are a commoditized commodity with massive aggregation competition. The acute, unsolved user pain point is the cognitive fatigue of *evaluating* listings against their personal background. Solving evaluation creates immediate value regardless of where the job was discovered.
* **What Was Sacrificed:** Zero automated job recommendations on day one; candidates must copy-paste JDs.
* **Dependencies:** None.
* **Metric & Experiment Affected:** North Star (W-HCCD), Time-to-Triage Decision, EXP-05.
* **Revisit Trigger:** If user qualitative feedback indicates $>60\%$ of candidates drop off because they have no job links to evaluate.

---

### RD-02: Structured Candidate Evidence Profile Built Before AI Recommendations

* **Context:** Generating AI career advice can be done superficially by asking a user for their desired job title and a brief prompt, or rigorously by parsing and verifying their full resume and project history.
* **Decision:** Enforce structured profile parsing and manual project verification (`Increment 1`) before permitting any job-fit evaluation (`Increment 2`).
* **Alternatives Considered:**
  1. *Allow zero-setup evaluations using ad-hoc text prompts.*
  2. *Rely solely on automated LinkedIn profile scraping.*
* **Rationale:** AI recommendations are only as reliable as the underlying candidate facts. Unverified, superficial inputs lead to generic, hallucinated advice that misleads candidates. A verified profile forms the immutable grounding baseline.
* **What Was Sacrificed:** Onboarding time increases from 30 seconds to ~3 minutes.
* **Dependencies:** Foundational prerequisite for `CAP-06`, `CAP-07`, `CAP-08`, `CAP-09`.
* **Metric & Experiment Affected:** Profile Creation Rate, Unsupported Evidence Rate, EXP-02.
* **Revisit Trigger:** If onboarding drop-off exceeds $40\%$ during initial profile setup.

---

### RD-03: Evidence Grounding Established as an Absolute Release Gate

* **Context:** LLM hallucinations are a known risk. We had to decide whether to ship fit recommendations with a disclaimer or enforce a strict statistical launch gate on grounding accuracy.
* **Decision:** Make an **Unsupported Evidence (Hallucination) Rate $<1.0\%$** a mandatory, non-negotiable launch gate for all AI releases.
* **Alternatives Considered:**
  1. *Ship with a standard "AI may make mistakes" disclaimer banner.*
  2. *Allow higher tolerance ($<5.0\%$) during early beta.*
* **Rationale:** If an AI Career Copilot tells a candidate they are a "Strong Fit" by inventing skills they do not possess, the candidate will fail the recruiter screening call and permanently lose trust in the product.
* **What Was Sacrificed:** Release speed; requires extensive red-teaming and prompt engineering before opening beta.
* **Dependencies:** Blocks graduation from Release 0 to Release 1.
* **Metric & Experiment Affected:** Unsupported Evidence Rate, Candidate Trust Score, AI Safety Gate.
* **Revisit Trigger:** Non-negotiable; safety thresholds can only be tightened, never loosened.

---

### RD-04: Raw JD Text Ingestion Sequenced Before Fragile URL Scraping

* **Context:** Job descriptions live behind dynamic JavaScript, authentication walls, and anti-bot protections (Cloudflare, LinkedIn logins).
* **Decision:** Build and optimize Raw JD Text Paste as the primary, 100% reliable ingestion path (`Increment 1`) before attempting URL ingestion (`Increment 4`).
* **Alternatives Considered:**
  1. *Build a complex headless browser scraping microservice for MVP.*
  2. *Rely exclusively on third-party URL parsing APIs.*
* **Rationale:** A broken scraper creates a complete blocker in the core user loop. Raw text paste has a $100\%$ success rate across any platform, PDF, or private email listing.
* **What Was Sacrificed:** Aesthetic convenience of single-click URL input during initial testing.
* **Dependencies:** Foundational prerequisite for `CAP-05` and `CAP-13`.
* **Metric & Experiment Affected:** Ingestion Success Rate, Ingestion Abandonment Rate, EXP-03.
* **Revisit Trigger:** When URL parser achieves $>90\%$ reliability across top 10 ATS platforms.

---

### RD-05: Opportunity Prioritization Sequenced to Follow Fit Analysis

* **Context:** Triage queues can be generated either by quick superficial keyword filtering or as the synthesized output of deep fit analysis.
* **Decision:** Sequence the 3-Tier Opportunity Queue (`Increment 3`) strictly downstream of deep fit and gap analysis (`Increment 2`).
* **Alternatives Considered:**
  1. *Provide a quick pre-filter queue based on title and location before fit analysis.*
* **Rationale:** Superficial keyword sorting reinforces the exact "spray-and-pray" mental model we are solving. High-confidence prioritization requires understanding nuanced gap severity (e.g., distinguishing a blocking 3-year experience gap from a learnable BI tool).
* **What Was Sacrificed:** Instant sorting speed.
* **Dependencies:** Requires `CAP-09` (5-Tier Qualitative Fit Engine).
* **Metric & Experiment Affected:** Time-to-Prioritization, Override Engagement Rate, EXP-04.
* **Revisit Trigger:** If users evaluate $>20$ JDs simultaneously and demand batch pre-sorting.

---

### RD-06: Application Tracking Integrated into Core MVP

* **Context:** Application tracking is often treated as a secondary feature deferred to post-MVP roadmap phases.
* **Decision:** Include lightweight Kanban tracking and immutable local JD snapshots directly in **Increment 3** of the MVP.
* **Alternatives Considered:**
  1. *Build fit analysis only and let users track jobs in external spreadsheets.*
* **Rationale:** Without tracking and persistent JD snapshots, the product is a transactional one-time calculator. Job postings frequently get taken down (404) once applications close; saving immutable snapshots ensures candidates retain their preparation context during interview callbacks.
* **What Was Sacrificed:** Engineering effort allocated to Kanban state management instead of advanced AI features.
* **Dependencies:** Requires `CAP-12` and `CAP-13`.
* **Metric & Experiment Affected:** 7-Day Triage Return Rate, Snapshot Reference Rate, North Star (W-HCCD).
* **Revisit Trigger:** If tracking usage remains $<10\%$ among active evaluators over 4 pilot weeks.

---

### RD-07: Validation-Gated Post-MVP Expansion Over Fixed Feature Commit

* **Context:** Product roadmaps often commit to rigid 12-month feature deliverables before validating the foundational product-market fit.
* **Decision:** Enforce that Post-MVP roadmap themes (GitHub ingestion, browser extensions, market drift radar) are strictly gated by passing the Phase 7 validation plan (EXP-01 through EXP-05).
* **Alternatives Considered:**
  1. *Commit to a fixed quarterly feature calendar.*
* **Rationale:** Committing to complex integrations (like GitHub code parsing) before proving that candidates understand and act on basic text-based fit evaluations results in wasted engineering capital.
* **What Was Sacrificed:** Long-term feature predictability for external stakeholders.
* **Dependencies:** Requires passing Release 1 and Release 2 exit criteria.
* **Metric & Experiment Affected:** All Phase 6 Outcome Metrics, EXP-05 Benchmark.
* **Revisit Trigger:** If EXP-05 passes with $>50\%$ decision time reduction, accelerate post-MVP intelligence timeline.
