# Now / Next / Later Framework

## Overview

The **Now / Next / Later** framework categorizes product capabilities into clear operational horizons based on strategic priority, risk resolution, and dependency progression.

This framework protects the product team from feature sprawl by establishing an unambiguous boundary between what is being built immediately to validate the core value proposition (**NOW**), what will follow once the core loop is proven (**NEXT**), speculative long-term opportunities (**LATER**), and capabilities that are explicitly rejected (**NOT PLANNED**).

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   NOW / NEXT / LATER HORIZONS                                    │
│                                                                                                  │
│  NOW (MVP Horizon)                                                                               │
│  Focus: Validate the Core Decision Loop & Grounded Fit Engine (Increments 1-4)                   │
│                                                                                                  │
│  NEXT (Post-MVP Fast Follows)                                                                    │
│  Focus: Ingestion Reliability, Workflow Friction Reduction, & Interview Context Depth            │
│                                                                                                  │
│  LATER (Expansion Horizon)                                                                       │
│  Focus: Portfolio Artifact Analysis, Deep Repository Parsing, & Longitudinal Growth              │
│                                                                                                  │
│  NOT PLANNED (Strict Exclusions & Anti-Goals)                                                    │
│  Mass Auto-Apply Bots | Hallucinated Resumes | Recruiter Spam Engines | Generic LMS Platforms    │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 1. NOW — MVP Core Decision Loop

**Strategic Horizon:** Current Execution Focus (Increments 1–4)  
**Primary Outcome:** Validate that explainable, evidence-grounded fit analysis increases decision quality and reduces cognitive fatigue for early-career candidates.

| Capability | Module | Strategic Justification | Phase 7 Gate |
| :--- | :--- | :--- | :--- |
| **Resume PDF Parsing & Profile** | Profile | Foundational candidate evidence required for comparative fit evaluation. | Usability Test |
| **Manual Profile & Project Editor** | Profile | Prevents LLM extraction errors; ensures candidate verified truth. | Grounding Audit |
| **Raw JD Text Ingestion Box** | Job Capture | 100% reliable input path bypassing ATS scraper/blocking failures. | EXP-03 |
| **4-Category Requirement Taxonomy** | Job Structuring | Disentangles hard requirements from nice-to-haves; eliminates noise. | Extraction Audit |
| **Demonstrated Match Mapping** | Fit Intelligence | Shows direct evidence matches with exact candidate profile citations. | EXP-02 |
| **Transferable Capability Overlaps** | Fit Intelligence | Helps candidates identify cross-domain strengths (e.g., Python for Analytics). | Usability Test |
| **4-Level Skill Gap Classification** | Fit Intelligence | Prevents irrational self-rejection by distinguishing blockers from learnables. | Usability Test |
| **5-Tier Qualitative Fit Engine** | Fit Intelligence | Replaces arbitrary match percentages with calibrated qualitative tiers. | EXP-01 |
| **Candidate Fit Manual Override** | Fit Intelligence | Preserves candidate agency; prevents algorithmic lock-in. | EXP-01 / EXP-04 |
| **Insufficient-Info Handling** | Fit Intelligence | AI explicitly flags ambiguous JDs rather than hallucinating answers. | Safety Gate |
| **3-Tier Opportunity Queue** | Decision Support | Automates triage categorization without taking away user control. | EXP-04 |
| **Immutable Local JD Snapshot** | Workflow Archive | Preserves JD text locally so candidates have context even if link dies. | Architecture Gate |
| **Kanban Application Tracking** | Workflow Archive | Eliminates spreadsheet fragmentation within the single decision workspace. | Workflow Test |
| **URL Ingestion with Fallback** | Job Capture | Convenient secondary ingestion with automatic fallback to text paste. | EXP-03 |
| **Ambiguity Warning Banners** | Job Structuring | Visual cue alerting user when a JD lacks key compensation/skill details. | Grounding Audit |
| **Interview Prep Context Drawer** | Workflow Depth | Contextual talking points grounded in demonstrated match evidence. | Pilot Validation |
| **Resume Narrative Framing Cues** | Workflow Depth | Contextual guidance on framing existing projects for specific JD gaps. | Pilot Validation |
| **Target Role Filter & Search** | Workflow Archive | Triage filtering across stored applications by status and role category. | Usability Test |

---

## 2. NEXT — Post-MVP Workflow Depth & Reliability

**Strategic Horizon:** Immediate Post-MVP Phase (Unlocks upon passing MVP Validation Gates)  
**Primary Outcome:** Deepen workflow retention, reduce repetitive input friction, and expand interview readiness support.

| Capability | Module | Strategic Justification | Trigger to Move to NOW |
| :--- | :--- | :--- | :--- |
| **Browser Extension Helper** | Job Capture | Allows 1-click text extraction directly on job boards without tab switching. | High MVP return rate + user demand for capture speed. |
| **Automated Stagnation Alerts** | Workflow Archive | Proactive nudges when bookmarked roles remain unapplied for $>5$ days. | User tracking drop-off observed in Phase 6 telemetry. |
| **Multi-Version Resume Linking** | Profile | Enables tagging specific resume variants (e.g., Data vs. BI) to distinct roles. | User portfolio feedback indicating multi-role search tracks. |
| **JD Keyword Normalizer Engine** | Job Structuring | Advanced semantic clustering for rare or quirky enterprise skill labels. | Extraction precision $<90\%$ on specialized roles. |
| **Interview Answer Frameworks** | Workflow Depth | Structured STAR-method prompts tailored to identified JD gap questions. | Strong usage of Increment 4 Interview Context Drawer. |
| **Batch JD Comparison Mode** | Decision Support | Side-by-side comparative fit evaluation for up to 3 similar job offers. | User requests for final offer selection decision support. |

---

## 3. LATER — Advanced Intelligence & Long-Term Horizon

**Strategic Horizon:** Growth & Scale (Contingent on demonstrated PMF and W-HCCD North Star validation)  
**Primary Outcome:** Leverage deep artifact analysis and contextual network intelligence to expand career decision power.

| Capability | Module | Strategic Justification | Validation Prerequisite |
| :--- | :--- | :--- | :--- |
| **GitHub Repository Deep Code Ingestion** | Profile Intelligence | Parses actual commit history, SQL scripts, and code quality as verified evidence. | Core text-profile fit analysis validated at scale. |
| **Live Portfolio & Tableau Artifact Ingestion** | Profile Intelligence | Ingests project reports, dashboards, and research papers into candidate evidence base. | High candidate demand for visual project verification. |
| **Role Evolution & Market Drift Radar** | Market Intelligence | Alerts candidate when industry demand shifts (e.g., dbt becoming standard for BI). | High cohort retention and multi-month active usage. |
| **Alumni & Peer Context Overlays** | Context Intelligence | Identifies alumni representation or hiring patterns at target company. | Strategic privacy review & partnership validation. |

---

## 4. NOT PLANNED — Explicitly Rejected Features & Anti-Goals

The following capabilities are **strictly excluded** from the roadmap. They contradict the product principles established in [02-Product-Strategy/product-principles.md](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/02-Product-Strategy/product-principles.md) and [05-Prioritization/trade-off-analysis.md](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/05-Prioritization/trade-off-analysis.md).

```
┌─────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   STRICTLY REJECTED ANTI-GOALS                                  │
├─────────────────────────────────────────────────────────────────────────────────────────────────┤
│ ❌ Automated Mass Auto-Apply Bots (Creates candidate spam, degrades trust, damages ATS reputation)│
│ ❌ Hallucinated Resume Fabricators (Generates unverified bullet points; violates safety gate)     │
│ ❌ Automated Recruiter Cold Outreach Spammers (Violates ethical boundaries; candidate liability)  │
│ ❌ Full-Fledged LMS / Video Course Platform (Drifts from core decision support into courseware) │
│ ❌ Single Numerical Fit Scores (Induces false precision, keyword gaming, and misapplication)    │
│ ❌ Social Feeds / Leaderboards / Peer Metrics (Generates toxic anxiety in early-career search)   │
└─────────────────────────────────────────────────────────────────────────────────────────────────┘
```
