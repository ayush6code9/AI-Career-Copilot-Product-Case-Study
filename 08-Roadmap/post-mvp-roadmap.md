# Post-MVP Product Roadmap

## Overview

The **Post-MVP Product Roadmap** outlines the strategic evolution of AI Career Copilot beyond the initial 18 MVP capabilities.

Following the core principle established in [08-Roadmap/roadmap-strategy.md](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/08-Roadmap/roadmap-strategy.md), post-MVP investment is **strictly gated by empirical validation** of the core decision loop. The product will not expand horizontally until the MVP proves that explainable fit evaluation drives high-confidence career decisions.

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   POST-MVP STRATEGIC THEMES                                      │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 1. RELIABILITY & INGESTION DEPTH  ──▶ Frictionless job capture across any source or format       │
│ 2. INTELLIGENCE & PORTFOLIO       ──▶ Deeper verified evidence (GitHub code, dashboards, SQL)    │
│ 3. WORKFLOW & INTERVIEW DEPTH     ──▶ STAR-method interview framing and longitudinal tracking    │
│ 4. CONTEXTUAL MARKET RADAR        ──▶ Market drift alerts and semantic skill clustering          │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Post-MVP Feature Categorization

### Theme 1: Reliability & Ingestion Depth

* **Browser Extension Capture Companion (`FEAT-P1-01`):**
  * *Capability:* Lightweight Chrome/Firefox extension that automatically extracts structured text from LinkedIn, Indeed, Handshake, and Greenhouse without manual copy-pasting.
  * *Value Add:* Reduces ingestion time from ~45 seconds to <5 seconds while preserving 100% snapshot fidelity.
  * *Activation Trigger:* User telemetry indicates $>50\%$ of weekly active users evaluate $>5$ jobs per week.

* **Advanced Semantic JD Keyword Normalizer (`FEAT-P1-02`):**
  * *Capability:* Maps proprietary corporate job buzzwords to standardized industry competencies (e.g., normalizes "Data Wrangler" to "Data Analyst with ETL focus").
  * *Value Add:* Eliminates false gap classifications caused by employer-specific vocabulary.
  * *Activation Trigger:* User manual overrides on skill taxonomy exceed $15\%$.

---

### Theme 2: Intelligence & Portfolio Reasoning

* **GitHub Repository & SQL Project Ingestion (`FEAT-P2-01`):**
  * *Capability:* Ingests public candidate GitHub repositories, analyzing commit history, README documentation, SQL queries, and Python notebooks as verified skill evidence.
  * *Value Add:* Bridges the gap for entry-level candidates whose resumes understate their actual hands-on technical capabilities.
  * *Activation Trigger:* Core text-profile fit analysis passes all grounding gates with $<0.5\%$ hallucination rate over 3 consecutive cohorts.

* **Interactive Dashboard & Case Study Artifact Parser (`FEAT-P2-02`):**
  * *Capability:* Allows candidates to upload Tableau public links, PowerBI screenshots, or product teardown PDFs into their verified evidence base.
  * *Value Add:* Provides grounded proof for Business Analyst and Product Analyst candidates who rely on visual project artifacts.
  * *Activation Trigger:* High adoption in business/product analyst user segments.

---

### Theme 3: Workflow & Interview Readiness Depth

* **Structured STAR-Method Interview Answer Frameworks (`FEAT-P1-03`):**
  * *Capability:* Automatically structures candidate demonstrated match evidence into Situation-Task-Action-Result (STAR) talking point templates tailored to specific JD requirements.
  * *Value Add:* Converts triage evaluation directly into interview readiness without external prep tools.
  * *Activation Trigger:* High engagement ($>40\%$) with Increment 4 Interview Context Drawer.

* **Multi-Track Search & Version Linking (`FEAT-P1-04`):**
  * *Capability:* Allows candidates targeting dual career tracks (e.g., Data Analyst vs. Software Engineer) to maintain track-specific candidate profiles and link appropriate resumes to matching roles.
  * *Value Add:* Prevents context pollution across divergent career aspirations.
  * *Activation Trigger:* User surveys reveal $>30\%$ of active users maintain multiple active resumes.

---

### Theme 4: Contextual Market Radar

* **Market Skill Demand Drift Alerts (`FEAT-P2-03`):**
  * *Capability:* Aggregates skill frequency across ingested candidate JDs to alert users when a specific tool or methodology is trending in their target role (e.g., "70% of your Data Analyst roles now list dbt as a core tool").
  * *Value Add:* Proactively directs candidate upskilling effort toward high-ROI capabilities.
  * *Activation Trigger:* Ingested JD archive reaches $>10,000$ unique normalized postings.

---

## 2. Post-MVP Prioritization & Gating Matrix

| Post-MVP Capability | Category | Source Priority | Strategic Impact | Complexity | Gating Precondition | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Browser Extension Companion** | Ingestion | P1 | High | Medium | MVP Ingestion Stability Validated | `[FUTURE]` |
| **STAR Interview Frameworks** | Workflow | P1 | High | Medium | Increment 4 Drawer Engagement $>40\%$ | `[FUTURE]` |
| **Multi-Track Profile Linking** | Profile | P1 | Medium | Medium | MVP Core Retention $>35\%$ | `[FUTURE]` |
| **Semantic Keyword Normalizer** | Structuring | P1 | Medium | High | Taxonomy Accuracy Audit Passed | `[FUTURE]` |
| **GitHub Repository Ingestion** | Intelligence | P2 | High | High | AI Grounding $<0.5\%$ Error Rate | `[FUTURE]` |
| **Portfolio & Artifact Parser** | Intelligence | P2 | Medium | High | Candidate Profile Completion $>85\%$ | `[FUTURE]` |
| **Market Skill Drift Radar** | Market Data | P2 | Medium | High | JD Corpus Scale $>10,000$ Postings | `[FUTURE]` |

---

## 3. Strict Boundary Enforcement (Permanent Anti-Goals)

Even as AI Career Copilot evolves post-MVP, the following product concepts remain **permanently excluded**:

```
┌─────────────────────────────────────────────────────────────────────────────────────────────────┐
│                               PERMANENT POST-MVP EXCLUSIONS                                     │
├─────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 1. ❌ Auto-Apply Bots / Headless Form Fillers:                                                  │
│    Will never be built. Dilutes candidate signal, creates spam, and triggers ATS blacklisting. │
├─────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 2. ❌ Generative Resume Fabrication:                                                            │
│    Will never invent ungrounded bullet points. System only optimizes framing of real evidence.  │
├─────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 3. ❌ Cold Outreach Recruiter Automation:                                                       │
│    Will never send unsolicited mass automated emails/DMs on behalf of candidates.               │
├─────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 4. ❌ Proprietary Job Board / Monolithic Aggregator:                                            │
│    Will not compete with LinkedIn/Indeed on horizontal scraping; value is decision intelligence.│
└─────────────────────────────────────────────────────────────────────────────────────────────────┘
```
