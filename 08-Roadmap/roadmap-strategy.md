# Roadmap Strategy & Philosophy

## Executive Summary

The **AI Career Copilot Product Roadmap** translates the strategic foundations established in Phases 1–7 (Problem Discovery, Product Strategy, UX Architecture, PRD, DAVR Prioritization, Metrics Telemetry, and Experimentation Framework) into an **outcome-oriented execution sequence**.

Rather than functioning as a static engineering sprint backlog or a feature-bloated Gantt chart, this roadmap serves as a **hypothesis-driven uncertainty reduction tool**. It dictates what capabilities must be delivered, the exact architectural dependencies governing their sequence, the experiment-backed validation gates required before progression, and what features are deliberately excluded to preserve product integrity.

```
┌─────────────────────────────────────────────────────────────────────────────────────────────┐
│                                 ROADMAP EXECUTION CHAIN                                     │
│                                                                                             │
│   Problem & JTBD (Phases 1-2)                                                               │
│        ↓                                                                                    │
│   PRD & UX Specifications (Phases 3-4)                                                      │
│        ↓                                                                                    │
│   DAVR Value-Risk Prioritization (Phase 5)                                                  │
│        ↓                                                                                    │
│   Telemetry & Validation Gates (Phases 6-7)                                                 │
│        ↓                                                                                    │
│   MVP Increments 1-4 [NOW] ➔ Reliability & Polish [NEXT] ➔ Intelligence Horizon [LATER]     │
│        ↓                                                                                    │
│   Decision: Retain, Iterate, or Rollback via Pre-Registered Decision Rules                  │
└─────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Core Roadmap Objective

The primary objective of this roadmap is to deliver the smallest credible version of AI Career Copilot that can rigorously validate the central product hypothesis:

> **Core Value Hypothesis [HYPOTHESIS]:**
> *"Providing early-career technical/analytical job seekers with an evidence-grounded, explainable fit breakdown across structured job descriptions will significantly increase decision quality, reduce triage fatigue, and eliminate low-fit misapplications compared to status-quo manual browsing and generic chatbot prompting."*

### What the Roadmap Optimizes For

1. **Closed Decision Loop Integrity:** Ensuring the candidate can execute the entire workflow (`Candidate Evidence ➔ JD Ingestion ➔ Structured Breakdown ➔ Grounded Fit Evaluation ➔ Prioritization ➔ Immutable Snapshot & Status Tracking`) seamlessly without context fragmentation.
2. **AI Grounding & Explainability:** Prioritizing verifiable quote-level citations and transparent gap categorizations over opaque "magic" match numbers.
3. **Candidate Agency & Control:** Enforcing frictionless manual overrides and editable profile/job data at every stage of the user journey.
4. **Ingestion & Archive Reliability:** Ensuring 100% operational ingestion fidelity via raw text paste and persistent local job snapshots that survive recruiter link removals.
5. **Progressive Learning over Speed:** Ensuring each execution increment provides clear behavioral telemetry to validate Phase 7 hypotheses before unlocking subsequent development.

### What the Roadmap Deliberately Does NOT Optimize For

* ❌ **Scraped Job Volume / Search Aggregation:** The product is not a job board aggregator; candidates bring roles from their preferred sources.
* ❌ **Application Spam / Auto-Apply Volume:** Strictly rejecting automated form-filling or blind mass submission tools that harm candidate reputation.
* ❌ **Feature Sprawl & Vanity UI:** Resisting peripheral add-ons (e.g., social feeds, peer leaderboards, ungrounded resume writers) that distract from core decision support.
* ❌ **Premature Horizontal Expansion:** Maintaining deep specialization in technical and analytical entry-level roles (Data Analyst, Business Analyst, Product Analyst, ML/SWE) before generalizing.

---

## 2. Product Roadmap vs. Engineering Task List

A fundamental Product Management standard enforced in this repository is the strict separation between a **Product Roadmap** and an **Engineering Implementation Task List**.

| Dimension | Product Roadmap (This Document) | Engineering Sprint Backlog (Implementation) |
| :--- | :--- | :--- |
| **Focus** | User problems, strategic capabilities, customer outcomes, and business value. | Technical tasks, class designs, database schemas, and framework configurations. |
| **Currency** | High-Confidence Career Decisions, reduced evaluation time, and candidate trust. | Story points, pull requests, test coverage %, and CI/CD pipelines. |
| **Items** | "Evidence-Grounded Fit Breakdown", "Immutable JD Snapshot", "3-Tier Opportunity Queue". | "Write PDF extraction regex", "Configure PostgreSQL foreign keys", "Setup FastAPI routes". |
| **Gating** | Experiment validation gates (EXP-01, EXP-02), guardrail metrics (Hallucination Rate $<1.0\%$). | Unit test passing, linting clean, staging environment deployment. |
| **Audience** | Product Managers, Founders, Strategic Stakeholders, Design Leads, PM Recruiters. | Software Engineers, QA Engineers, DevOps/Infrastructure Specialists. |

---

## 3. Guiding Roadmap Principles

### Principle 1: Value-Risk Sequencing (DAVR Alignment)
As established in [05-Prioritization/prioritization-framework.md](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/prioritization-framework.md), sequencing follows the Dependency-Aware Value-Risk (DAVR) framework. High-value foundational capabilities that resolve high uncertainty are built first; high-risk speculative features are deferred.

### Principle 2: Hard Technical Dependencies Dictate the Critical Path
An AI system cannot perform comparative fit evaluation without structured candidate evidence, and cannot structure requirements without normalized job description ingestion. The roadmap enforces strict topological sequencing:
$$\text{Candidate Profile} \longrightarrow \text{JD Ingestion} \longrightarrow \text{Requirement Taxonomy} \longrightarrow \text{Fit Analysis} \longrightarrow \text{Queue Prioritization} \longrightarrow \text{Snapshot Tracking}$$

### Principle 3: Validation Gates Before Capability Expansion
No roadmap increment graduates to broad release or unlocks dependent features without passing its pre-registered Phase 7 experiment criteria and Phase 6 telemetry guardrails.

```
┌─────────────────┐      Pass Validation Gate      ┌─────────────────┐
│ Increment N     │ ─────────────────────────────▶ │ Increment N+1   │
│ Capabilities    │                                │ Capabilities    │
└─────────────────┘                                └─────────────────┘
         │
         │ Fail Guardrail (e.g., Hallucination ≥ 1.0%)
         ▼
┌─────────────────┐
│ Kill-Switch /   │
│ Redesign UX     │
└─────────────────┘
```

### Principle 4: Preserving Product Truth (Anti-Fabrication)
All future milestones, capabilities, and dates represent planned analytical allocations. No completed velocity, user adoption, conversion rates, or revenue numbers are fabricated.

*Status Legend:*
* `[PLANNED]`: Approved for future execution in the designated increment.
* `[VALIDATION REQUIRED]`: Implementation dependent on passing an explicit experimentation gate.
* `[PRODUCT INFERENCE]`: PM strategic deduction based on desk research and workflow analysis.
