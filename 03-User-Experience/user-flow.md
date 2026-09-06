# End-to-End User Flow

This document details the complete operational user journey for both first-time and returning candidates using **AI Career Copilot**.

---

## 1. Primary User Journey Architecture

```
[1. ONBOARD] ──▶ [2. CREATE PROFILE] ──▶ [3. DISCOVER / INGEST] ──▶ [4. ANALYZE FIT]
       │                   │                       │                     │
       ▼                   ▼                       ▼                     ▼
[5. REVIEW REASONING] ──▶ [6. PRIORITIZE] ──▶ [7. ACT / APPLY] ──▶ [8. TRACK & RETURN]
```

---

## 2. Step-by-Step Flow Specification

### Step 1: Onboarding
* **User Goal**: Understand what the product does and evaluate if it helps their entry-level job search.
* **User Action**: Lands on entry page; clicks "Get Started" or "Evaluate a Job".
* **System Response**: Displays concise 3-step value intro: *Import Profile ➔ Analyze Job Fit ➔ Prioritize Pipeline*.
* **Decision Point**: Sign in with Google / GitHub or continue with a guest session `[ASSUMPTION]`.
* **Possible Failure State**: Bounce due to perceived signup friction or generic marketing copy.
* **Next Step**: Transition immediately to Profile Setup.

### Step 2: Create Candidate Profile (Zero-Friction Baseline)
* **User Goal**: Input qualifications without spending 30 minutes filling out manual forms.
* **User Action**: Uploads PDF resume or pastes text summary + GitHub/portfolio URL; selects target roles (e.g., Data Analyst, AI/ML Engineer).
* **System Response**: Automatically parses and structures skills, capstone projects, coursework, and target role preferences into an editable profile card in <5 seconds `[PRODUCT INFERENCE]`.
* **Decision Point**: Candidate reviews extracted skills and confirms or edits missing project nuances.
* **Possible Failure State**: Resume parser misreads unstructured project text or omits key tools.
* **Next Step**: Transition to Job Ingestion / Discovery.

### Step 3: Discover & Ingest Job Description
* **User Goal**: Bring an ambiguous job opportunity into the decision copilot.
* **User Action**: Pastes a job listing URL or raw JD text from LinkedIn, Indeed, Handshake, or company career portal.
* **System Response**: Instantly sanitizes text, extracts metadata (Company, Title, Location, Experience Level), and confirms receipt `[PRODUCT INFERENCE]`.
* **Decision Point**: Candidate confirms role title and company name before initiating analysis.
* **Possible Failure State**: Ingested text is too short (<50 words) or broken URL scraper fails due to login wall.
* **Next Step**: Transition to Fit Analysis Engine.

### Step 4: Analyze Fit (Explainable Extraction)
* **User Goal**: Evaluate how their specific profile matches the complex requirements of the JD.
* **User Action**: Clicks "Analyze Opportunity Fit".
* **System Response**: Displays an interactive analysis state with progress indicators (*Extracting Core Prerequisites ➔ Mapping Candidate Projects ➔ Identifying Gaps*).
* **Decision Point**: None (automated cognitive processing).
* **Possible Failure State**: Ambiguous JD contains zero technical requirements (e.g., pure corporate marketing fluff).
* **Next Step**: Renders the complete Job-Fit Explanation screen.

### Step 5: Review Match Explanation (Core Decision Screen)
* **User Goal**: Understand *why* the job matches or does not match, and identify real vs. artificial gaps.
* **User Action**: Inspects the 3 core buckets: **Demonstrated Core Matches**, **Transferable Overlaps**, and **Missing Requirements / Gaps**.
* **System Response**: Highlights explicit evidence citations from candidate profile (e.g., *"Your PyTorch Capstone demonstrates ML Modeling requirement"*).
* **Decision Point**: Does candidate agree with the fit assessment? Should this opportunity be prioritized for an application?
* **Possible Failure State**: Candidate feels an AI inference misinterpreted a project's depth.
* **Next Step**: Candidate clicks "Add to Priority Queue" or "Save to Pipeline" or "Discard".

### Step 6: Prioritize (Opportunity Queue Triage)
* **User Goal**: Organize multiple analyzed roles into clear execution tiers to decide where to invest application effort.
* **User Action**: Views the Opportunity Queue, grouped by **High-Fit Target**, **Reach / Stretch**, and **Low Match**.
* **System Response**: Reorders opportunities by fit conviction, deadline urgency, and candidate target preferences `[PRODUCT INFERENCE]`.
* **Decision Point**: Candidate selects the top 2–3 roles to actively apply to in this session.
* **Possible Failure State**: All analyzed roles appear in the "Stretch" tier, causing candidate anxiety.
* **Next Step**: Candidate opens the highest-priority role card and prepares to apply.

### Step 7: Act / Apply (Guided Direct Submission)
* **User Goal**: Submit a high-quality, targeted application on the employer portal without context loss.
* **User Action**: Clicks "Apply on Company Site" (opens official external portal) while keeping AI Career Copilot side-panel open for project framing notes.
* **System Response**: Archives the evaluated JD snapshot, candidate match notes, and timestamps the application event.
* **Decision Point**: Candidate completes official form on employer portal and returns to Copilot.
* **Possible Failure State**: Candidate abandons application on employer portal due to 10-page Workday questionnaire.
* **Next Step**: Candidate toggles status to "Applied" in Copilot.

### Step 8: Track & Return (Continuous Pipeline Intelligence)
* **User Goal**: Maintain clean status records without manual spreadsheet logging; retrieve exact JD when contacted for interviews.
* **User Action**: Views Kanban pipeline (Saved ➔ Applied ➔ Screening ➔ Interview ➔ Offer); updates cards as recruiter emails arrive.
* **System Response**: Stores snapshot permanently; surfaces interview prep context and match strengths upon clicking any card `[PRODUCT INFERENCE]`.
* **Decision Point**: Move card to next interview round or archive as "Rejected / No Response".
* **Possible Failure State**: Candidate forgets to update status for several weeks.
* **Next Step**: Re-enters discovery loop for subsequent application cycles.

---

## 3. Critical Product Moments

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CRITICAL MOMENTS (WOW MOMENTS)                  │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Instant Profile Extraction:                                         │
│    Uploading a resume produces a structured, editable portfolio in 3s. │
│ 2. Explainable Fit Breakdown:                                          │
│    Seeing transparent evidence citations ("PyTorch project maps to     │
│    TensorFlow JD requirement") instead of a vague percentage score.    │
│ 3. Automated Queue Triage:                                             │
│    Transforming 20 chaotic open tabs into 3 clear priority tiers.      │
│ 4. Recruiter Call Snapshot Retrieval:                                  │
│    Instantly pulling up the exact, archived JD and match strengths     │
│    when an employer calls weeks later for a phone screen.              │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 4. Friction Points & UX Mitigations

| Friction Point | Root Risk | UX Mitigation |
| :--- | :--- | :--- |
| **Profile Setup Drop-off** | Candidate dislikes filling long profile forms `[ASSUMPTION]`. | 1-click Resume / LinkedIn PDF upload with zero mandatory form fields beyond email `[PRODUCT INFERENCE]`. |
| **Job Description Ingestion Barrier** | Browser login walls or complex URL scraping failures `[FACT]`. | Prominent fallback to 1-click "Paste Raw JD Text" with automatic formatting `[PRODUCT INFERENCE]`. |
| **Pipeline Maintenance Abandonment** | Candidate forgets to update spreadsheet-like trackers `[FACT]`. | 1-click status pills directly on the job analysis card without requiring navigation to a separate tracker screen `[PRODUCT INFERENCE]`. |

---

## 5. Trust & Transparency Moments

* **AI Uncertainty Indicator**: When a JD is poorly written, the UI explicitly displays: *"⚠️ Ambiguous JD: Requirement depth is unstated in posting. Review recommended before applying."*
* **Evidence Linkage**: Every green "Matched" tag features an inspectable tooltip showing the exact bullet point from the candidate's resume that justified the match `[PRODUCT INFERENCE]`.
* **Zero Fabrication Guarantee**: The system never invents skills or infers tools that are absent from the candidate's verified profile data `[PRODUCT INFERENCE]`.
