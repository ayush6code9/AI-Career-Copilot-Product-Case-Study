# Core User Workflow (Primary Decision Loop)

This document specifies the primary interaction loop of **AI Career Copilot**, designed specifically to fulfill the core Job to Be Done:

> *"When I find an entry-level job posting with an extensive list of requirements, I want to instantly see a clear breakdown of how my skills and projects align with the role, so I can determine whether this opportunity is genuinely worth my time to pursue."*

---

## 1. Decision Loop Workflow Architecture

```
[1. JOB FOUND] ──▶ [2. IMPORTED] ──▶ [3. PARSED] ──▶ [4. STRUCTURED] ──▶ [5. COMPARED]
                                                                               │
                                                                               ▼
[9. TRACK/APPLY] ◀── [8. USER DECIDES] ◀── [7. REASONING REVIEWED] ◀── [6. FIT GENERATED]
```

---

## 2. Step-by-Step Decision Transformation Specification

### Step 1: Job Found (Discovery Origin)
* **Input**: An open job listing found by candidate on LinkedIn, Indeed, Handshake, or company career portal `[FACT]`.
* **Transformation**: Candidate copies link or text of the interesting posting.
* **Output**: Raw URL or unstructured JD clipboard content.
* **User Decision**: *"Does this title and company look interesting enough to evaluate?"* `[ASSUMPTION]`.
* **Trust Requirement**: Low (pure external exploration).

---

### Step 2: Job Imported (Ingestion Interface)
* **Input**: Pasted URL or pasted raw JD text into AI Career Copilot ingestion modal.
* **Transformation**: System ingests text, strips boilerplate CSS/HTML headers, extracts company metadata `[PRODUCT INFERENCE]`.
* **Output**: Sanitized job text container with auto-detected metadata: **Job Title**, **Company**, **Location**, and **Workplace Type** (Remote/Hybrid/Onsite).
* **User Decision**: Verify that the auto-detected title and company match the target listing.
* **Trust Requirement**: Confirmation that the correct job content was captured without truncation.

---

### Step 3: Job Parsed & Cleaned
* **Input**: Sanitized job description text.
* **Transformation**: System segments unstructured narrative paragraphs into discrete analytical blocks (Company Context, Core Responsibilities, Technical Stack, Qualifications) `[PRODUCT INFERENCE]`.
* **Output**: Standardized JD entity structure.
* **User Decision**: None (automated system transition in <1s).
* **Trust Requirement**: System preserves original wording without hallucinating or adding imaginary requirements.

---

### Step 4: Requirements Structured (Taxonomy Mapping)
* **Input**: Standardized JD entity structure.
* **Transformation**: Requirements are categorized using our 6-tier ontology: **Hard Requirements**, **Core Competencies**, **Preferred Tools**, and **Ambiguous Wording** `[PRODUCT INFERENCE]`.
* **Output**: Tiered requirement checklist separating non-negotiable prerequisites from secondary wishlist items.
* **User Decision**: Candidate sees a scannable summary of what the company actually demands.
* **Trust Requirement**: Clear distinction between genuine prerequisites and inflated preferences.

---

### Step 5: Candidate Profile Compared (Contextual Alignment)
* **Input**: Tiered JD requirements + Candidate Profile (structured skills, academic coursework, capstone projects, GitHub repos).
* **Transformation**: System matches candidate project evidence and coursework against tiered JD requirements, evaluating semantic and domain equivalence `[PRODUCT INFERENCE]`.
* **Output**: Bidirectional mapping matrix (JD Requirement ➔ Candidate Evidence).
* **User Decision**: None (processing step).
* **Trust Requirement**: Matching must reference candidate's verified input data rather than assuming unstated background.

---

### Step 6: Fit Explanation Generated (Explainability Engine)
* **Input**: Bidirectional mapping matrix.
* **Transformation**: Synthesizes qualitative assessment tier (*Strong Fit*, *Reasonable Fit*, *Stretch Opportunity*, *Low Match*) and natural language rationale `[PRODUCT INFERENCE]`.
* **Output**: Multi-dimensional Job-Fit Breakdown card rendering:
  1. Overall Qualitative Tier
  2. Demonstrated Strengths & Evidence Links
  3. Transferable Equivalencies
  4. Addressable Gaps (differentiated into Blocker vs. Learnable)
  5. Actionable Next Step Recommendation.
* **User Decision**: None (rendering output).
* **Trust Requirement**: **Critical Trust Threshold**. The explanation must be completely transparent, logical, and evidence-cited.

---

### Step 7: User Reviews Reasoning (The Aha! Moment)
* **Input**: Multi-dimensional Job-Fit Breakdown card.
* **Transformation**: Candidate consumes the structured rationale in <90 seconds, replacing 30 minutes of manual tab confusion.
* **Output**: Candidate mental clarity on qualification alignment and gap severity `[ASSUMPTION]`.
* **User Decision**:
  * *"Is this assessment accurate?"*
  * *"Are the missing gaps things I can learn quickly or bridge with an existing project?"*
  * *"Do I want to invest effort in applying?"*
* **Trust Requirement**: User can click any highlighted requirement to see the exact resume bullet that justified the match.

---

### Step 8: User Decides (Strategic Triage)
* **Input**: Candidate judgment formed after reviewing explainable fit.
* **Transformation**: Candidate selects one of three actionable paths:
  1. **"High-Fit Target"** ➔ Move to Priority Queue to apply immediately.
  2. **"Stretch / Save for Later"** ➔ Save to Pipeline with gap notes.
  3. **"Discard / Low Fit"** ➔ Remove from active queue to eliminate tab clutter.
* **Output**: Structured status transition.
* **User Decision**: Explicit commitment of candidate time and bandwidth `[PRODUCT INFERENCE]`.
* **Trust Requirement**: Reversibility—candidate can retrieve discarded roles or change priority tiers at any time.

---

### Step 9: Track & Apply (Context Archival)
* **Input**: Prioritized job card + Candidate action.
* **Transformation**:
  * If applying: Opens employer application URL in new tab while locking a permanent snapshot of the evaluated JD and match notes in Copilot tracker `[PRODUCT INFERENCE]`.
  * Candidate completes submission on company site and marks status as "Applied".
* **Output**: Persistent application record in Kanban tracker (`APPLIED` column) with zero context loss.
* **User Decision**: Transition back to discovery queue or close session feeling organized and confident.
* **Trust Requirement**: Permanent local archival ensuring data is never lost when employer closes the live job posting `[FACT]`.

---

## 3. Workflow Summary Matrix

| Step | Primary Actor | Cognitive Effort | Time Required | Output Deliverable |
| :--- | :---: | :---: | :---: | :--- |
| **1. Find Job** | User | Low | External | Live Posting URL / Text |
| **2. Ingest** | User / System | Zero | < 5 sec | Standardized Job Container |
| **3. Parse & Structure** | System | Zero | < 2 sec | Tiered Requirements Schema |
| **4. Compare Profile** | System | Zero | < 2 sec | Alignment Matrix |
| **5. Generate Fit** | System | Zero | < 3 sec | Explainable Fit Summary |
| **6. Review Reasoning**| User | **Medium (High Value)** | **60–90 sec** | **Conviction & Gap Clarity** |
| **7. Decide & Triage** | User | Low | < 10 sec | Priority Assignment |
| **8. Track & Apply** | User / System | Low | 1-click | Archived Snapshot & Kanban Card |
