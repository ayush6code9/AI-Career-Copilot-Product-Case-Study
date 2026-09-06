# Low-Fidelity Wireframe Specifications

This document defines the structural layout, component hierarchy, functional states, and AI trust mechanics for the 8 core screens of **AI Career Copilot**.

---

## Screen Directory Overview

```
┌────────────────────────────────────────────────────────────────────────┐
│ 1. Welcome / Onboarding Screen                                         │
│ 2. Candidate Profile Setup Screen                                      │
│ 3. Job Ingestion & Discovery Screen                                    │
│ 4. Job Details & Requirement Structuring Screen                        │
│ 5. Job-Fit Analysis & Explainability Screen (Core MVP Screen)          │
│ 6. Opportunity Queue & Prioritization Screen                           │
│ 7. Application Tracking Pipeline Screen (Kanban View)                  │
│ 8. Interview Preparation & Saved Context Drawer                        │
└────────────────────────────────────────────────────────────────────────┘
```

---

## Screen 1: Welcome / Onboarding Screen

* **Screen Purpose**: Introduce value proposition, eliminate confusion, and motivate first-time candidate signup/import.
* **Primary User Goal**: Understand what the product does and start profile setup in <30 seconds.
* **Key Components**:
  * Hero Section: Headline (*"Cut through job description noise with explainable AI career decision support"*).
  * 3-Step Decision Loop visual: *Import Profile ➔ Analyze Job Fit ➔ Prioritize Queue*.
  * 1-Click Action Card: "Upload Resume to Begin".
* **Primary CTA**: `[ Upload Resume (PDF / DOCX) ]`
* **Secondary Actions**: `[ Paste LinkedIn Profile Text ]`, `[ View Interactive Demo Role ]`.
* **Information Hierarchy**:
  1. Value Headline & Subtitle
  2. Quick Upload Box (drag-and-drop zone)
  3. "How AI Career Copilot Works" 3-card explainer.
* **Empty State**: Clean drop-zone with file format tags (`.pdf`, `.docx`).
* **Loading State**: Subtle upload progress bar with status text (*"Reading resume sections..."*).
* **Error State**: Non-supported file format warning with clear instruction (*"Please upload a standard text PDF or DOCX"*).
* **AI Trust / Transparency**: Privacy badge: *"Your resume is processed privately and never shared with recruiters or sold to third parties."*
* **Transition to Next Screen**: On successful upload/parse, auto-transitions to **Screen 2 (Candidate Profile)**.

---

## Screen 2: Candidate Profile Setup Screen

* **Screen Purpose**: Allow candidate to review, refine, and verify their extracted skills, coursework, capstone projects, and target role preferences.
* **Primary User Goal**: Confirm an accurate baseline profile so AI matching produces high-conviction assessments.
* **Key Components**:
  * Extracted Skill Chips (grouped by: Languages, Frameworks, Analytics/Data Tools).
  * Project Evidence Cards (Title, Tech Stack, 2-bullet summary, GitHub link input).
  * Academic Background (Degree, Major, Graduation Date).
  * Target Roles Selector (Tags: Data Analyst, Product Analyst, ML Engineer, Software Engineer).
* **Primary CTA**: `[ Save Profile & Evaluate Jobs ]`
* **Secondary Actions**: `[ + Add Custom Skill ]`, `[ + Add Project ]`, `[ Re-upload Resume ]`.
* **Information Hierarchy**:
  1. Profile Completeness Indicator ("Baseline Ready")
  2. Target Roles & Preferences
  3. Verified Project Cards
  4. Extracted Skills & Coursework.
* **Empty State**: Empty input pills prompting: *"Add at least 1 capstone project or core technical skill"*.
* **Loading State**: Skeleton card loading while parsing resume text into structured fields.
* **Error State**: Inline red validation on empty mandatory fields (e.g., Target Role unselected).
* **AI Trust / Transparency**: Every auto-extracted skill features an edit/delete icon, reinforcing candidate agency over their data.
* **Transition to Next Screen**: Transitions to **Screen 3 (Job Ingestion & Discovery)**.

---

## Screen 3: Job Ingestion & Discovery Screen

* **Screen Purpose**: Provide frictionless ingestion of any job posting from any external job board or URL.
* **Primary User Goal**: Ingest an ambiguous external job posting for instant analysis.
* **Key Components**:
  * Dual-Mode Input Tab: **[ Ingest via URL ]** / **[ Paste Job Description Text ]**.
  * Input Form: URL input field or Multi-line Text Area.
  * Recent Ingestions Sidebar (History of last 5 analyzed roles).
* **Primary CTA**: `[ Analyze Job Fit ]`
* **Secondary Actions**: `[ Clear Input ]`, `[ Load Sample Entry-Level JD ]`.
* **Information Hierarchy**:
  1. Ingestion Mode Switcher (URL vs. Raw Text)
  2. Main Text / URL Input Container
  3. Auto-detected Metadata Confirmation Preview.
* **Empty State**: Clean input field with placeholder: *"Paste a LinkedIn / Indeed / Handshake job posting URL or raw JD text..."*
* **Loading State**: Ingestion spinner (*"Fetching job description and extracting requirement entities..."*).
* **Error State**: Ingestion error alert (*"Could not fetch URL due to login restriction. Please copy and paste the raw JD text directly."*) with 1-click fallback.
* **AI Trust / Transparency**: Explicit character count counter and clear parsing scope indicators.
* **Transition to Next Screen**: Transitions directly to **Screen 5 (Fit Analysis & Explainability)** upon clicking CTA.

---

## Screen 4: Job Details & Requirement Structuring Screen (Audit View)

* **Screen Purpose**: Provide complete auditability of the raw job description versus the structured requirements parsed by the system.
* **Primary User Goal**: Inspect raw JD content to confirm the AI did not hallucinate or omit critical employer criteria.
* **Key Components**:
  * Split-Pane Layout:
    * Left Pane: Full Raw Job Description (preserved text).
    * Right Pane: Structured Entity Checklist (**Core Prerequisites**, **Preferred Tools**, **Experience Level**, **Domain Context**).
* **Primary CTA**: `[ Proceed to Fit Analysis ]`
* **Secondary Actions**: `[ Edit Detected Criteria ]`, `[ Back to Ingestion ]`.
* **Information Hierarchy**:
  1. Job Title, Company, Location header
  2. Structured vs. Raw side-by-side comparison
  3. JD Ambiguity & Confidence Badge.
* **Empty State**: N/A (always loaded with an active JD).
* **Loading State**: Shimmering side-by-side skeleton blocks.
* **Error State**: *"Unstructured text: Unable to identify standard technical criteria"* with manual override tools.
* **AI Trust / Transparency**: Direct visual mapping between raw text highlighted phrases and structured requirement tags.
* **Transition to Next Screen**: Advances to **Screen 5 (Fit Analysis)**.

---

## Screen 5: Job-Fit Analysis & Explainability Screen (Core MVP Screen)

* **Screen Purpose**: Deliver transparent, explainable decision-support answering: *"Should I apply to this job and why?"*
* **Primary User Goal**: Understand qualification alignment, project evidence matches, and addressable gaps in <90 seconds.
* **Key Components**:
  * Top Summary Banner: **Qualitative Assessment Badge** (*"Strong Fit — Target Opportunity"* | Confidence: High).
  * Strategic Recommendation Box (*Why to apply, what to emphasize, what to verify*).
  * 3 Expandable Requirement Columns:
    1. **🟢 Demonstrated Matches** (Citing candidate projects).
    2. **🟡 Transferable Overlaps** (Citing conceptual coursework equivalents).
    3. **🔴 Addressable Gaps** (Classified into *Blocking*, *Important*, or *Learnable on Job*).
* **Primary CTA**: `[ ★ Add to Priority Queue ]`
* **Secondary Actions**: `[ 💾 Save to Pipeline ]`, `[ ✕ Discard / Low Conviction ]`, `[ View Raw JD ]`.
* **Information Hierarchy**:
  1. Overall Recommendation Tier & Confidence Rating
  2. Strategic Action Guidance
  3. Detailed Requirement & Evidence Breakdown
  4. Gap Categorization & Remediation Advice
  5. Action Toolbar.
* **Empty State**: N/A (rendered upon analysis completion).
* **Loading State**: Step-by-step progress checklist animation (*"Comparing project evidence... Categorizing gaps..."*).
* **Error State**: Low-confidence warning banner if JD is too vague: *"⚠️ Low Signal JD. Review recommended."*
* **AI Trust / Transparency**: Every green match chip contains an expandable tooltip showing the exact verified bullet point from candidate profile.
* **Transition to Next Screen**: Clicking "Add to Priority Queue" transitions to **Screen 6 (Opportunity Queue)**.

---

## Screen 6: Opportunity Queue & Prioritization Screen

* **Screen Purpose**: Transform 30+ chaotic open opportunities into an ordered, actionable execution queue for active application sessions.
* **Primary User Goal**: Decide which 3–5 applications to submit during the current job-search session.
* **Key Components**:
  * Priority Tiers:
    * **Tier 1: High-Fit Targets (High Conviction)**
    * **Tier 2: Growth Reach / Stretch (1–2 Learnable Gaps)**
    * **Tier 3: Low Conviction / Safety**
  * Opportunity Cards: Company, Role, Key Strengths, Gap Summary, Deadline Urgency.
  * Triage Toolbar: Filter by Role Category, Sort by Match Conviction / Date Added.
* **Primary CTA on Card**: `[ Apply on Employer Site ↗ ]`
* **Secondary Actions**: `[ Move to Pipeline (Applied) ]`, `[ Change Priority Tier ]`, `[ Archive ]`.
* **Information Hierarchy**:
  1. Queue Summary Counter (e.g., *"4 High-Fit Targets Ready to Apply"*)
  2. Tier 1 Grouping (Top Cards)
  3. Tier 2 Grouping
  4. Quick Ingest Header Button.
* **Empty State**: Graphic showing empty queue with prompt: *"No prioritized jobs yet. Ingest a job description to build your queue."*
* **Loading State**: Skeleton card list with pulsing priority badges.
* **Error State**: Toast notification on connection failure.
* **AI Trust / Transparency**: Candidates can drag and drop cards to manually override AI priority tier rankings.
* **Transition to Next Screen**: Clicking a card opens **Screen 8 (Interview Context Drawer)**; marking as applied moves to **Screen 7 (Kanban Tracker)**.

---

## Screen 7: Application Tracking Pipeline Screen (Kanban View)

* **Screen Purpose**: Provide a clean, unified status pipeline to monitor active applications and prevent spreadsheet abandonment.
* **Primary User Goal**: Track application progression from submission to offer with zero manual data entry overhead.
* **Key Components**:
  * Kanban Columns: **[ Prioritized ]** ➔ **[ Applied ]** ➔ **[ Screening ]** ➔ **[ Interview ]** ➔ **[ Offer ]**.
  * Pipeline Card: Company Logo/Initials, Job Title, Days in Stage, Fit Badge, Snapshot Available Icon.
  * Quick-Move Arrows & Drag-and-Drop functionality.
  * Collapsible Archive Panel: `[ Rejected / Withdrawn (12) ]`.
* **Primary CTA**: `[ + Ingest New Job ]`
* **Secondary Actions**: `[ Filter by Status ]`, `[ Export Application Log (CSV) ]`.
* **Information Hierarchy**:
  1. Pipeline Metrics Header (*Active: 8 | Screening: 2 | Interviews: 1*)
  2. Kanban Board Columns
  3. Card Detail Drawer (Slide-out).
* **Empty State**: Column-specific empty placeholders (e.g., *"No active interviews yet. Keep submitting your High-Fit targets!"*).
* **Loading State**: Shimmering Kanban column skeletons.
* **Error State**: Reversion of card position with toast message if drag-and-drop sync fails.
* **AI Trust / Transparency**: Every card shows a permanent badge indicating: *"🔒 JD Snapshot Archived"*.
* **Transition to Next Screen**: Clicking any card slides out **Screen 8 (Context Drawer)**.

---

## Screen 8: Job Detail & Interview Preparation Context Drawer

* **Screen Purpose**: Eliminate context loss during recruiter screening calls by instantly surfacing the exact archived JD, match strengths, and notes.
* **Primary User Goal**: Retrieve complete application context in <10 seconds when a recruiter calls or schedules an interview.
* **Key Components**:
  * Slide-out Drawer Panel (overlays tracker without full-page navigation).
  * **Interview Cheat Sheet**:
    * 3 Key Highlight Strengths to mention during call.
    * 2 Prepared Answers for addressable gaps.
  * Full Archived JD Snapshot (immutable text).
  * Candidate Custom Notes & Interaction Log (Date applied, recruiter contact).
* **Primary CTA**: `[ Log Interview Date / Move Stage ]`
* **Secondary Actions**: `[ Copy Match Summary ]`, `[ Print / PDF Export ]`, `[ Close Drawer ]`.
* **Information Hierarchy**:
  1. Role Title, Company & Applied Date Header
  2. Interview Cheat Sheet Box (Key talking points)
  3. Identified Strengths & Project Evidence
  4. Full Archived Job Description.
* **Empty State**: N/A (only accessed from an existing card).
* **Loading State**: Instant drawer animation (data cached locally with zero network lag).
* **Error State**: Fallback text if snapshot corrupt: *"Raw text recovered from local cache."*
* **AI Trust / Transparency**: Clearly demarcates between *Original Employer JD Text* and *AI-Generated Talking Points*.
* **Transition to Next Screen**: Clicking outside or "Close" collapses drawer back to **Screen 7 (Kanban)**.
