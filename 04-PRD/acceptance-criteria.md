# Acceptance Criteria Specification

This document provides formal, testable acceptance criteria formatted in the standard **Given / When / Then / And** (Gherkin) framework for all MVP functional requirements of **AI Career Copilot**.

---

## 1. Candidate Profile (CP)

### AC-CP-001: Resume Upload & Parsing
* **Given** a user is on the Profile Onboarding or Settings screen,
* **When** the user uploads a valid resume file (`.pdf` or `.docx`, <5MB),
* **Then** the system shall parse the document and auto-populate the candidate's technical skills, capstone projects, academic major, and graduation date within 5 seconds `[DESIGN TARGET]`,
* **And** display a visual confirmation showing the extracted data fields for user verification,
* **And** if the file is corrupted, image-only, or password-protected, the system shall display an error toast explaining the issue and provide a fallback text-paste box.

### AC-CP-002: Profile Manual Verification & Skill Editing
* **Given** a candidate profile has been populated from a resume,
* **When** the user views the structured profile card,
* **Then** the user shall be able to add new skills, delete misidentified skills, edit project bullet descriptions, and input GitHub project URLs,
* **And** any changes saved by the user shall become the definitive profile state used in subsequent fit evaluations.

### AC-CP-003: Target Role & Workplace Preferences
* **Given** a user is finalizing their baseline profile,
* **When** the user selects 1 to 3 target role categories (e.g., Data Analyst, AI/ML Engineer) and workplace preferences (Remote, Hybrid, Onsite),
* **Then** the system shall save these preferences to filter and calibrate subsequent opportunity prioritization.

---

## 2. Job Discovery & Ingestion (JD)

### AC-JD-001: Raw Job Description Text Ingestion
* **Given** a user has copied text from an external job board,
* **When** the user pastes the text into the Job Ingestion text area (≥50 characters) and clicks "Analyze Job Fit",
* **Then** the system shall sanitize the input, auto-detect the Job Title and Company Name (or prompt the user if unstated), and initiate the parsing pipeline.

### AC-JD-002: Job URL Ingestion & Fallback
* **Given** a user is on the Ingestion screen,
* **When** the user submits a live job posting URL,
* **Then** the system shall attempt to extract the job title, company name, location, and raw JD text,
* **And** if scraping fails due to authentication or paywalls, the system shall prompt the user with: *"Unable to access this URL directly. Please copy and paste the job text below"* without losing entered URL context.

---

## 3. Job Parsing & Requirement Structuring (PS)

### AC-PS-001: Multi-Tier Requirement Segmentation
* **Given** raw job description text has been ingested,
* **When** the parsing engine processes the text,
* **Then** the system shall decompose the JD into discrete requirement entities:
  1. *Hard Non-Negotiables* (e.g., degree requirements, work authorization),
  2. *Core Technical Competencies* (primary daily tools/languages),
  3. *Preferred Qualifications* (bonus frameworks),
  4. *Domain / Context Criteria*,
* **And** present these entities in an audit view separating raw text from structured items.

### AC-PS-002: Ambiguous JD Detection
* **Given** an ingested job description contains fewer than 3 concrete technical skills or consists primarily of generic marketing boilerplate,
* **When** the parsing engine completes extraction,
* **Then** the system shall assign a "Low Signal / Ambiguous" flag to the job,
* **And** display a prominent amber banner: *"⚠️ Low Signal JD: Ambiguous requirements detected. Fit confidence is limited."*

---

## 4. Job-Fit Analysis & Explainability (FA)

### AC-FA-001: Multi-Dimensional Fit Decomposition
* **Given** a verified candidate profile and a structured job description,
* **When** the user initiates fit analysis,
* **Then** the system shall compare candidate evidence against JD requirements and classify every requirement into one of 5 visual buckets:
  1. **Demonstrated Core Match** (direct profile evidence),
  2. **Transferable Match** (conceptual or equivalent tooling),
  3. **Preferred Skill Match / Bonus**,
  4. **Addressable Gap**,
  5. **Unclear / Vague Requirement**,
* **And** the system shall render this breakdown in under 3 seconds `[DESIGN TARGET]`.

### AC-FA-002: Grounded Evidence Citations (Zero Fabrication)
* **Given** the system has marked a requirement as a "Demonstrated Core Match",
* **When** the user hovers over or clicks on the matched skill chip,
* **Then** the system shall display an inspectable tooltip citing the exact resume bullet, capstone project title, or coursework topic that justified the match,
* **And** the system shall never fabricate or extrapolate experiences not present in the candidate's profile.

### AC-FA-003: Categorized Gap Severity Tiers
* **Given** the candidate profile lacks evidence for one or more extracted JD requirements,
* **When** the fit breakdown is rendered,
* **Then** the system shall segment each missing requirement into one of four distinct gap severity tiers:
  * **Blocking Gap** (e.g., missing mandatory degree level or legal visa requirement),
  * **Important Gap** (core tool missing with no transferable equivalent),
  * **Learnable on the Job** (secondary tool learnable in <10 hours),
  * **Nice-to-Have** (explicitly listed as preferred/bonus),
* **And** provide a concise 1-line guidance note explaining how to address each gap.

### AC-FA-004: Qualitative Overall Assessment Tiering (No Numerical Scores)
* **Given** the requirement classification and gap analysis are complete,
* **When** the overall assessment is rendered,
* **Then** the system shall assign exactly one of 5 qualitative tiers:
  * **Strong Fit (Target Opportunity)**
  * **Reasonable Fit (Viable Application)**
  * **Stretch Opportunity (Reach / 1–2 Learnable Gaps)**
  * **Low Fit (Misaligned / Major Blockers)**
  * **Insufficient Information (Vague JD)**
* **And** the UI shall not display any single numerical or percentage match score (e.g., "78%").

---

## 5. Opportunity Prioritization (PR)

### AC-PR-001: Opportunity Queue Triage
* **Given** a candidate has evaluated multiple job descriptions,
* **When** the user navigates to the Opportunity Queue,
* **Then** the system shall group opportunities into 3 actionable sections:
  * **Tier 1: High-Fit Targets**
  * **Tier 2: Growth Reach / Stretch**
  * **Tier 3: Low Conviction / Archive**,
* **And** order cards within each tier by fit conviction, role preference alignment, and date added.

### AC-PR-002: Manual Priority Override
* **Given** an opportunity card is placed in an AI-assigned tier,
* **When** the candidate manually changes the tier dropdown or drags the card to another tier,
* **Then** the system shall immediately update the card's priority state, persist the user's manual override, and flag the card as *"User Prioritized"*.

---

## 6. Application Tracking & Context Archival (TR)

### AC-TR-001: Persistent Job Description Snapshot
* **Given** an analyzed job is saved or moved to "Prioritized",
* **When** the save event occurs,
* **Then** the system shall create an immutable local snapshot containing:
  1. Full raw JD text,
  2. Extracted requirement entities,
  3. Generated fit analysis & evidence citations,
  4. Candidate custom notes & application timestamp,
* **And** ensure this snapshot remains permanently accessible even if the external posting URL returns a 404 or is deleted by the employer.

### AC-TR-002: Kanban Pipeline Status Updates
* **Given** a candidate has saved jobs in their tracking board,
* **When** the user drags a card across stages (`SAVED` ➔ `REVIEWED` ➔ `PRIORITIZED` ➔ `APPLIED` ➔ `SCREENING` ➔ `INTERVIEW` ➔ `OFFER` ➔ `REJECTED` / `WITHDRAWN`),
* **Then** the system shall update the card's status in <200ms, update the timestamp, and record the stage progression in the application history log.

### AC-TR-003: Interview Preparation Context Retrieval
* **Given** an application card is in the `APPLIED`, `SCREENING`, or `INTERVIEW` state,
* **When** the user clicks on the card,
* **Then** the system shall open a slide-out drawer rendering the "Interview Context Cheat Sheet",
* **And** surface the top 3 highlighted project strengths to mention during recruiter calls, the full immutable JD text, and candidate submission notes in <500ms.
