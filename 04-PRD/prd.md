# AI Career Copilot — Product Requirements Document (PRD)

| Metadata Attribute | Value |
| :--- | :--- |
| **Document Status** | Draft / Portfolio Case Study |
| **Document Version** | 1.0 |
| **Product Owner** | Senior Product Manager (Case Study Author) |
| **Product Stage** | MVP Definition & Technical Hand-off Ready |
| **Last Updated** | 2026-09-06 |
| **Related Documents** | [Problem Statement](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/01-Problem-Discovery/problem-statement.md) \| [Product Strategy](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/02-Product-Strategy/product-vision.md) \| [User Experience](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/03-User-Experience/user-flow.md) \| [Acceptance Criteria](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/04-PRD/acceptance-criteria.md) |

---

## 1. Executive Summary

**AI Career Copilot** is a candidate-centric career decision-support system designed to solve the cognitive evaluation and prioritization bottlenecks faced by final-year students and recent graduates in technical and analytical fields.

Rather than building an automated spam-application bot or a passive job aggregator, AI Career Copilot translates ambiguous job descriptions into **transparent, explainable qualification breakdowns** (Demonstrated Matches, Transferable Overlaps, Categorized Gaps), prioritizes opportunities into actionable tiers, and preserves immutable job snapshots across a unified Kanban pipeline. The MVP focuses strictly on high-conviction decision quality and context retention.

```
DISCOVER  ──▶  UNDERSTAND  ──▶  EVALUATE  ──▶  PRIORITIZE  ──▶  ACT  ──▶  TRACK
```

---

## 2. Product Context & Strategic Alignment

### 2.1 Problem Reference
`[FACT]` Entry-level hiring has become hyper-competitive and fragmented across dozens of job boards.  
`[PRODUCT INFERENCE]` Candidates suffer from severe decision paralysis because job descriptions conflate mandatory prerequisites with aspirational wishlists, job platforms offer opaque keyword badges, and candidates lack explainable tools to benchmark their project and academic evidence against corporate criteria.

### 2.2 Why Now?
* **Proliferation of Auto-Apply Bots**: Mass-apply bots have flooded recruiters with low-intent applications, forcing companies to implement defensive ATS filtering. Candidates now need *higher conviction and tailored relevance*, not more automated volume `[DESK RESEARCH]`.
* **Maturity of LLM Information Extraction**: Large Language Models have reached sufficient semantic reasoning to reliably extract structured entities from unstructured text and map academic coursework to corporate tooling `[FACT]`.

### 2.3 Target User & Ideal Customer Profile (ICP)
* **Primary Target Segment**: Final-year undergraduate/master's students and recent graduates (< 1 year post-graduation) seeking their first professional full-time role `[FACT]`.
* **Target Roles**: Data Analyst, Business Analyst, Product Analyst, AI/ML Engineer, Software Engineer, GenAI Developer.
* **Key Persona**: *Aarav (Final-Year Senior)* — constrained by 8–12 hours/week amidst exams/capstones, possesses concrete project evidence, needs fast qualification conviction `[ASSUMPTION]`.

### 2.4 Primary Job to Be Done (JTBD)
> **"When I find an entry-level job posting with an extensive list of requirements, I want to instantly see a clear breakdown of how my skills and projects align with the role, so I can determine whether this opportunity is genuinely worth my time to pursue."**

### 2.5 Existing Alternatives & Gaps
* **Job Boards (LinkedIn, Indeed)**: Monetize employer listing volume; provide opaque, black-box keyword badges `[FACT]`.
* **Ad-Hoc LLM Prompting (ChatGPT)**: Disjointed, lacks persistent candidate profile state, no multi-job triage or tracking `[PRODUCT INFERENCE]`.
* **Spreadsheets / Notion**: Manual data entry; completely disconnected from live job data; links break when postings close `[FACT]`.

---

## 3. Product Goals & Non-Goals

### 3.1 Primary Goal
* **PG-01 (Decision Velocity & Clarity)**: Enable early-career candidates to accurately evaluate qualification fit and gap severity for any technical job posting in under 90 seconds `[DESIGN TARGET]`, eliminating guesswork and imposter self-disqualification.

### 3.2 Secondary Goals
* **PG-02 (Effort Optimization)**: Transform chaotic 30-tab search sessions into an ordered queue of top 5–10 high-conviction target opportunities `[DESIGN TARGET]`.
* **PG-03 (Zero Context Loss)**: Guarantee 100% preservation of evaluated job descriptions and match notes throughout the application and interview lifecycle `[FACT]`.

### 3.3 Explicit Non-Goals (Out of Scope)
* **NG-01: Auto-Submission Bots**: We will NOT build automated browser bots that submit applications without candidate involvement.
* **NG-02: Generic Resume Mass Rewriter**: We will NOT generate synthetic, hallucinated resumes to game ATS filters.
* **NG-03: Employer Recruitment Portal**: We will NOT sell candidate data or build employer-facing recruitment screening tools.
* **NG-04: Non-Technical Role Expansion**: We will NOT support non-technical domains (Sales, Marketing, Design) in the initial release.

---

## 4. MVP Scope Definition

The MVP delivers 5 foundational, tightly integrated modules:

```
┌────────────────────────────────────────────────────────────────────────┐
│                               MVP SCOPE                                │
├───────────────────┬───────────────────┬────────────────────────────────┤
│ 1. CANDIDATE      │ 2. JOB INGESTION  │ 3. JOB-FIT ANALYSIS            │
│    PROFILE        │    & DISCOVERY    │    (Explainability Engine)     │
│ 1-click resume    │ Raw text & URL    │ Qualitative tiers, evidence    │
│ parsing, verified │ ingestion with    │ popovers, categorized gap      │
│ project baseline. │ auto-metadata.    │ severity tiers.                │
├───────────────────┴───────────────────┼────────────────────────────────┤
│ 4. OPPORTUNITY PRIORITIZATION         │ 5. APPLICATION TRACKING        │
│ Tiered triage queue (Target /         │ Kanban pipeline with permanent │
│ Stretch / Low Conviction).            │ immutable JD snapshots.        │
└───────────────────────────────────────┴────────────────────────────────┘
```

| Module | User Problem Addressed | User Value Delivered | Inclusion Justification |
| :--- | :--- | :--- | :--- |
| **1. Candidate Profile** | Manual form fatigue during onboarding `[PP-08]`. | Auto-populates skills, capstones, and preferences in <60s. | Foundational baseline required for all AI match comparisons. |
| **2. Job Ingestion** | Fragmentation across job boards `[PP-01]`. | Ingests job descriptions from any board via URL or raw text. | Allows users to evaluate opportunities from any source. |
| **3. Job-Fit Analysis** | Opaque match badges and bloated JDs `[PP-03, PP-05]`. | Transparent requirement breakdown with grounded evidence citations. | **Core Value Engine**: Delivers primary product decision support. |
| **4. Prioritization** | Bandwidth dilution and 30-tab paralysis `[PP-07]`. | Ranks roles into High-Fit, Stretch, and Low Conviction tiers. | Optimizes weekly candidate application time. |
| **5. Application Tracking** | Expired JD links and context loss `[PP-09]`. | Permanent JD snapshots and Kanban progression for interview prep. | Closes the loop from evaluation to interview screening. |

---

## 5. User Flows

### 5.1 First-Time User Flow
`Landing / Welcome Screen ➔ Upload Resume PDF ➔ Verify Extracted Skills/Projects ➔ Paste First Job Description ➔ Review Job-Fit Explanation ➔ Add to Priority Queue ➔ View Tracking Board.`

### 5.2 Returning User Flow
`Open Application ➔ Ingest New Job Posting OR View Opportunity Queue ➔ Execute Top Prioritized Role ➔ Click "Apply on Company Site" ➔ Toggle Status to "Applied" ➔ Access Saved Snapshots during Recruiter Calls.`

---

## 6. Functional Requirements (FR)

### 6.1 Candidate Profile (CP)
| ID | Functional Requirement | User Value | Priority | Dependency |
| :--- | :--- | :--- | :---: | :--- |
| **FR-CP-001** | The system shall allow users to upload a resume file in `.pdf` or `.docx` format (<5MB). | Zero-friction onboarding. | **Must Have** | None |
| **FR-CP-002** | The system shall automatically extract technical skills, tools, coursework, and project descriptions from the resume into structured fields. | Eliminates manual profiling. | **Must Have** | FR-CP-001 |
| **FR-CP-003** | The system shall allow users to manually add, edit, or delete skills and project descriptions. | Guarantees user agency and accuracy. | **Must Have** | FR-CP-002 |
| **FR-CP-004** | The system shall allow users to select 1 to 3 target role categories (Data Analyst, Business Analyst, Product Analyst, AI/ML, SWE). | Calibrates evaluation context. | **Must Have** | None |
| **FR-CP-005** | The system shall allow users to attach GitHub repository links and project URLs to specific profile projects. | Enhances technical evidence depth. | **Should Have** | FR-CP-003 |

### 6.2 Job Ingestion & Discovery (JD)
| ID | Functional Requirement | User Value | Priority | Dependency |
| :--- | :--- | :--- | :---: | :--- |
| **FR-JD-001** | The system shall allow users to paste raw job description text into a multi-line input box. | Universal compatibility with all portals. | **Must Have** | None |
| **FR-JD-002** | The system shall allow users to input a job posting URL and attempt automated text extraction. | Reduces copy-paste friction. | **Should Have** | None |
| **FR-JD-003** | The system shall auto-detect and populate Job Title, Company Name, and Workplace Type (Remote/Hybrid/Onsite) upon ingestion. | Minimizes manual data entry. | **Must Have** | FR-JD-001 |
| **FR-JD-004** | The system shall provide a clear error message and fallback text box if URL scraping fails. | Graceful degradation. | **Must Have** | FR-JD-002 |

### 6.3 Job Parsing & Requirement Structuring (PS)
| ID | Functional Requirement | User Value | Priority | Dependency |
| :--- | :--- | :--- | :---: | :--- |
| **FR-PS-001** | The system shall parse unstructured JD text into discrete requirement entities: Hard Prerequisites, Core Competencies, Preferred Tools, and Domain Criteria. | Eliminates JD ambiguity. | **Must Have** | FR-JD-001 |
| **FR-PS-002** | The system shall detect and display an audit view comparing raw JD text against extracted entities. | Builds transparent trust. | **Should Have** | FR-PS-001 |
| **FR-PS-003** | The system shall identify and flag low-signal or ambiguous job descriptions (<3 technical criteria or heavy marketing fluff). | Prevents false confidence. | **Must Have** | FR-PS-001 |

### 6.4 Job-Fit Analysis & Explainability (FA)
| ID | Functional Requirement | User Value | Priority | Dependency |
| :--- | :--- | :--- | :---: | :--- |
| **FR-FA-001** | The system shall compare candidate profile evidence against extracted JD requirements and generate a multi-dimensional fit breakdown. | Core decision support. | **Must Have** | FR-CP-002, FR-PS-001 |
| **FR-FA-002** | The system shall assign exactly one qualitative assessment tier to the evaluated job: *Strong Fit*, *Reasonable Fit*, *Stretch Opportunity*, *Low Fit*, or *Insufficient Information*. | Eliminates misleading scores. | **Must Have** | FR-FA-001 |
| **FR-FA-003** | The system shall provide inspectable evidence citations linking every demonstrated match to verified candidate profile text. | Eliminates AI hallucination doubt. | **Must Have** | FR-FA-001 |
| **FR-FA-004** | The system shall classify all missing skills into 4 distinct severity tiers: *Blocking*, *Important*, *Learnable on Job*, and *Nice-to-Have*. | Prevents imposter self-disqualification. | **Must Have** | FR-FA-001 |
| **FR-FA-005** | The system shall generate actionable recommendation guidance (Why to apply, what to emphasize in narrative, pre-submission checks). | Turns analysis into action. | **Should Have** | FR-FA-001 |
| **FR-FA-006** | The system shall strictly prohibit the display of any single percentage or numerical match score. | Enforces product principle #1. | **Must Have** | FR-FA-002 |

### 6.5 Opportunity Prioritization (PR)
| ID | Functional Requirement | User Value | Priority | Dependency |
| :--- | :--- | :--- | :---: | :--- |
| **FR-PR-001** | The system shall aggregate analyzed opportunities into a prioritized queue structured into 3 distinct tiers: High-Fit Targets, Growth Stretch, and Low Conviction. | Eliminates tab paralysis. | **Must Have** | FR-FA-002 |
| **FR-PR-002** | The system shall allow users to manually re-order cards or override an AI-assigned priority tier with 1 click. | Preserves candidate agency. | **Must Have** | FR-PR-001 |
| **FR-PR-003** | The system shall provide filters by target role category and sorting by date added or fit conviction. | Enhances sprint efficiency. | **Should Have** | FR-PR-001 |

### 6.6 Application Tracking & Context Archival (TR)
| ID | Functional Requirement | User Value | Priority | Dependency |
| :--- | :--- | :--- | :---: | :--- |
| **FR-TR-001** | The system shall automatically capture and persist an immutable text snapshot of the raw JD, metadata, and match breakdown upon saving. | Guarantees zero context loss. | **Must Have** | FR-FA-001 |
| **FR-TR-002** | The system shall provide an interactive Kanban board supporting 7 active stages: `SAVED`, `REVIEWED`, `PRIORITIZED`, `APPLIED`, `SCREENING`, `INTERVIEW`, and `OFFER`. | Replaces spreadsheets. | **Must Have** | FR-TR-001 |
| **FR-TR-003** | The system shall provide an expandable archive for `REJECTED` and `WITHDRAWN` applications. | Maintains clean active board. | **Must Have** | FR-TR-002 |
| **FR-TR-004** | The system shall provide a 1-click slide-out "Interview Context Cheat Sheet" rendering highlighted strengths, gap answers, and full JD snapshot. | Accelerates interview prep. | **Should Have** | FR-TR-001 |

---

## 7. Fit Analysis Detailed Specification

```
┌────────────────────────────────────────────────────────────────────────┐
│                     FIT ANALYSIS EXTRACTION & MATCH ENGINE             │
├────────────────────────────────────────────────────────────────────────┤
│ 1. REQUIREMENT TAXONOMY:                                               │
│    • Hard Non-Negotiables: Legal authorization, degree level.          │
│    • Core Competencies: Primary languages & tools (Python, SQL, etc).  │
│    • Preferred Tools: Bonus libraries (Airflow, Docker, Tableau).      │
│    • Ambiguous Criteria: Generic corporate phrasing.                  │
│                                                                        │
│ 2. MATCH CLASSIFICATION RULES:                                         │
│    • Demonstrated Match: Direct semantic match to verified evidence.   │
│    • Transferable Match: Conceptual/tool equivalence (PyTorch➔TF).    │
│    • Preferred Match: Candidate has listed bonus skill.               │
│    • Missing Skill: Required tool absent from profile.                 │
│                                                                        │
│ 3. QUALITATIVE ASSESSMENT TIERS (Mutually Exclusive):                  │
│    • Strong Fit: 100% hard requirements met + ≥80% core stack.         │
│    • Reasonable Fit: Hard requirements met + core transferable tools.  │
│    • Stretch Opportunity: Foundational match + 1 substantial gap.      │
│    • Low Fit: Hard requirement violation or misaligned discipline.     │
│    • Insufficient Information: <3 technical criteria detected.        │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 8. Requirements Traceability Matrix

| User Story | Functional Requirement | Acceptance Criteria | Related Phase 1 Problem / JTBD |
| :--- | :--- | :--- | :--- |
| **US-CP-01** (Resume Upload) | `FR-CP-001`, `FR-CP-002` | `AC-CP-001` | `PP-08` / `JTBD 1` |
| **US-CP-02** (Skill Verification) | `FR-CP-003` | `AC-CP-002` | `PP-04` / `JTBD 1` |
| **US-JD-01** (Raw Text Ingestion) | `FR-JD-001`, `FR-JD-003` | `AC-JD-001` | `PP-01` / `JTBD 1` |
| **US-JD-02** (URL Ingestion) | `FR-JD-002`, `FR-JD-004` | `AC-JD-002` | `PP-01` / `JTBD 1` |
| **US-FA-01** (Explainable Breakdown) | `FR-FA-001`, `FR-FA-002` | `AC-FA-001`, `AC-FA-004` | `PP-05` / `JTBD 1` |
| **US-FA-02** (Gap Severity Tiers) | `FR-FA-004` | `AC-FA-003` | `PP-06` / `JTBD 3` |
| **US-FA-03** (Evidence Citations) | `FR-FA-003` | `AC-FA-002` | `PP-05` / `JTBD 1` |
| **US-FA-04** (Ambiguous JD Warning) | `FR-PS-003` | `AC-PS-002` | `PP-03` / `JTBD 1` |
| **US-PR-01** (Opportunity Queue) | `FR-PR-001` | `AC-PR-001` | `PP-07` / `JTBD 2` |
| **US-PR-03** (Priority Override) | `FR-PR-002` | `AC-PR-002` | `PP-07` / `JTBD 2` |
| **US-TR-01** (JD Snapshot Archival) | `FR-TR-001` | `AC-TR-001` | `PP-09` / `JTBD 5` |
| **US-TR-02** (Kanban Pipeline Board) | `FR-TR-002`, `FR-TR-003` | `AC-TR-002` | `PP-09` / `JTBD 5` |
| **US-TR-03** (Interview Cheat Sheet)| `FR-TR-004` | `AC-TR-003` | `PP-09` / `JTBD 5` |

---

## 9. Non-Functional Requirements (NFR)

* **NFR-01 (Performance & Latency)**: Resume parsing shall complete in <5s; Job-fit analysis shall render in <3s `[DESIGN TARGET]`. Progress indicators must display real-time status during processing.
* **NFR-02 (Reliability & Persistence)**: Saved job snapshots and candidate profile states shall persist reliably in local storage state with zero loss upon browser refresh `[FACT]`.
* **NFR-03 (Privacy & PII Protection)**: Candidate resume data shall be processed privately; zero candidate profile information shall be shared with external recruitment entities `[FACT]`.
* **NFR-04 (Explainability & Auditability)**: 100% of generated match assertions must be traceable to candidate input text or flagged as unverified `[PRODUCT INFERENCE]`.
* **NFR-05 (Accessibility & Usability)**: Color-coded match chips must include text labels and icons to ensure WCAG AA compliance for color-blind users `[FACT]`.

---

## 10. AI Product Requirements & Trust Guardrails

| Guardrail ID | AI Safety Principle | User Risk Prevented | Enforcement Mechanism |
| :--- | :--- | :--- | :--- |
| **AI-REQ-01** | **Zero Experience Invention** | Prevents candidate false confidence and embarrassing interview disqualification. | Extraction prompt enforces strict JSON schema; unstated skills are marked "Missing". |
| **AI-REQ-02** | **Source Demarcation** | Prevents confusing employer mandates with AI interpretation. | Visual container separation between *Raw Employer JD* and *AI Match Notes*. |
| **AI-REQ-03** | **Calibrated Ambiguity Alerts** | Prevents candidate over-reliance on vague job listings. | Amber warning badge when JD text contains <3 concrete criteria. |
| **AI-REQ-04** | **No Outcome Promises** | Prevents legal and ethical misrepresentation. | Language explicitly framed as *"Qualification Alignment"*, never *"Guaranteed Hire"*. |
| **AI-REQ-05** | **User Reversibility & Editing** | Prevents LLM misinterpretation errors from locking user data. | 1-click editing for all extracted skills and priority assignments. |

---

## 11. Edge Cases & System Handling

### 11.1 Resume Edge Cases
* **Empty / Unparseable PDF**: Display inline error: *"Could not extract text from document. Please ensure PDF contains selectable text or paste resume text directly."*
* **Candidate Has Zero Listed Projects**: Display guidance nudge: *"Adding at least 1 academic capstone or course project significantly improves fit accuracy."*

### 11.2 Job Description Edge Cases
* **Extremely Brief JD (<50 words)**: System flags as *Insufficient Information* and prompts: *"This JD is too short for detailed fit analysis. Please paste full posting text if available."*
* **Contradictory Requirements (e.g., Entry-Level title requiring 5 years exp)**: System extracts "5 years" as an *Important Gap* but flags the role as *Experience Inflation Warning*.
* **Expired Job URL**: System displays graceful scraping error with 1-click fallback to paste raw text.

### 11.3 Fit Analysis Edge Cases
* **Conflicting Candidate Signals**: If resume mentions "Python" in coursework but not in projects, system classifies as *Transferable / Foundational Match* with explanatory note.
* **100% Skill Mismatch**: System cleanly assigns *Low Fit (Misaligned)* tier and explicitly lists the blocker disciplines.

---

## 12. MVP Priority Justification (MoSCoW)

* **Must Have**: Resume parsing, manual profile editing, raw text ingestion, explainable fit analysis (5 qualitative tiers, evidence citations, gap severity tiers), opportunity queue, persistent JD snapshotting, Kanban status updates.
* **Should Have**: URL ingestion with fallback, target role filtering, interview context cheat sheet drawer, ambiguous JD warning badge.
* **Could Have**: GitHub repo URL metadata linking, CSV export of application log.
* **Won't Have (MVP)**: Auto-submission bots, ATS resume rewriting, automated cold recruiter messaging, full LMS course recommendations.

---

## 13. Product Risks & Mitigation Matrix

| Risk ID | Risk Description | Prob. | Impact | Mitigation Strategy | Owner |
| :--- | :--- | :---: | :---: | :--- | :--- |
| **R-01** | **LLM Hallucination / Misattribution** | Med | High | Strict schema grounding; inspectable evidence tooltips citing raw resume text. | Product / AI |
| **R-02** | **Candidate False Confidence** | Med | High | Qualitative tiers instead of percentage scores; prominent ambiguity warnings. | PM / UX |
| **R-03** | **Job Scraping Fragility (URL Walls)** | High | Med | Prioritize 1-click raw text pasting as primary, highly reliable ingestion mode. | Eng / PM |
| **R-04** | **Pipeline Abandonment** | Med | Med | 1-click status pills on analysis cards; zero mandatory spreadsheet fields. | UX / Design |
| **R-05** | **Scope Creep into Auto-Apply** | Low | High | Strict enforcement of Product Principle #3 (Candidate Agency). | PM |

---

## 14. Assumptions & Validation Plan

| Assumption ID | Key Assumption | Why It Matters | Validation Method | Falsification / Pivot Trigger |
| :--- | :--- | :--- | :--- | :--- |
| **A-PRD-01** | Candidates prefer qualitative tiers over single percentage scores. | Core UX differentiator. | Track qualitative feedback and user preference sentiment during beta testing `[HYPOTHESIS]`. | If users demand numerical rankings, test hybrid score + explainability. |
| **A-PRD-02** | 1-click resume PDF upload eliminates onboarding drop-off. | Drives top-of-funnel activation. | Measure onboarding completion rate (>80% target) `[DESIGN TARGET]`. | If PDF parsing failure rate is high, introduce quick-start guided chip selector. |
| **A-PRD-03** | Preserving JD snapshots reduces interview anxiety. | Validates tracking value. | Measure frequency of opening the Interview Cheat Sheet drawer prior to interviews `[HYPOTHESIS]`. | If unused, simplify tracker to basic list view. |

---

## 15. Qualitative Success Criteria (MVP Baseline)

`[DESIGN SUCCESS CRITERIA]`
1. **Explainability Comprehension**: 100% of analyzed roles provide an explicit rationale separating Demonstrated Matches, Transferable Skills, and Gaps.
2. **Prioritization Utility**: Users can categorize and triage 10 ingested roles into actionable priority tiers in <5 minutes.
3. **Context Persistence**: 100% of saved opportunities retain immutable job descriptions and match notes across session restarts.

---

## 16. Product Decision Log

| # | Product Decision | Alternatives Considered | Decision Rationale | Product Consequence |
| :- | :--- | :--- | :--- | :--- |
| **1** | **Explainability Over Scores** | Single % score (e.g. "82%") | Single scores convey false precision and fail to explain *why* `[PRODUCT INFERENCE]`. | UI centers on 3-bucket requirement breakdown. |
| **2** | **Exclude Auto-Apply Bots** | 1-click automated ATS form submission | Spam bots harm candidate brand and degrade interview readiness `[DESK RESEARCH]`. | System directs user to official portal for direct submission. |
| **3** | **Include Integrated Tracking** | Standalone analysis tool; export to Notion | Expired job links cause critical context loss during recruiter calls `[FACT]`. | System persists immutable local JD snapshots. |
| **4** | **Qualitative Fit Tiers** | 1–10 star ratings | 5 qualitative tiers reflect realistic hiring ambiguity without pseudo-precision `[PRODUCT INFERENCE]`. | Tier badges: Strong Fit, Reasonable, Stretch, Low, Vague. |
| **5** | **Explicit User Confirmation** | Auto-adding all ingested jobs to board | Prevents pipeline clutter and enforces deliberate decision-making `[ASSUMPTION]`. | Ingested jobs remain in triage view until saved. |
| **6** | **Categorized Gap Severity** | Flat list of missing keywords | Distinguishes fatal blockers from 2-hour learnable syntax tools `[PRODUCT INFERENCE]`. | Prevents unnecessary candidate self-disqualification. |
