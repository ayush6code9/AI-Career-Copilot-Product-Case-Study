# Application Tracking & Context Archival UX

This document specifies the pipeline management and context-retention interface for **AI Career Copilot**, designed to eliminate context loss when employers reach out weeks after an application was submitted.

---

## 1. Application Lifecycle States

```
[SAVED] ──▶ [REVIEWED] ──▶ [PRIORITIZED] ──▶ [APPLIED] ──▶ [SCREENING] ──▶ [INTERVIEW] ──▶ [OFFER]
                                                                                │
                                                                                ├──▶ [REJECTED]
                                                                                └──▶ [WITHDRAWN]
```

---

## 2. State-by-State Specification

| Pipeline State | Why It Exists | Primary User Action | Information Captured | Recommended Next Action |
| :--- | :--- | :--- | :--- | :--- |
| **1. SAVED** | Bookmarks a raw job listing for later analysis without losing the link `[FACT]`. | Clicks "Save" or pastes JD link. | Job Title, Company, Ingested URL, Ingestion Timestamp. | Run "Analyze Fit" to evaluate qualification match. |
| **2. REVIEWED** | Signifies that the candidate has inspected the AI fit breakdown and understands requirement alignment `[PRODUCT INFERENCE]`. | Consumes explainable fit card. | Match Breakdown, Extracted Strengths, Gap Severity Tiers. | Assign priority tier or discard. |
| **3. PRIORITIZED** | Marks opportunity as a top-target application for the current weekly session `[PRODUCT INFERENCE]`. | Clicks "Add to Priority Queue". | Priority Rank, Target Application Date, Submission Notes. | Click "Apply on Company Site" to complete application. |
| **4. APPLIED** | Confirms candidate submitted official application on employer career portal `[FACT]`. | Clicks "Mark as Applied". | Date Applied, Resume Version Used, Portal Confirmation ID (optional). | Set reminder for follow-up timeline (e.g., 10 days). |
| **5. SCREENING** | Recruiter or HR coordinator reaches out for an initial phone screen `[FACT]`. | Drags card to "Screening"; logs interview date. | Recruiter Name, Screening Date/Time, Call Notes. | **Review Preserved Snapshot**: Inspect key strengths and framed project notes. |
| **6. INTERVIEW** | Advanced round (Technical screen, Hiring Manager, or Take-home assessment) `[FACT]`. | Drags card to "Interview". | Interview Round Type, Panelist Notes, Assessment Links. | Review role-specific tech stack and gap remediation checklist. |
| **7. OFFER** | Formal offer letter extended to candidate `[FACT]`. | Drags card to "Offer". | Compensation, Deadline, Role Title, Benefits Notes. | Compare offers against career goals. |
| **8. REJECTED** | Application declined or automated rejection email received `[FACT]`. | Marks card as "Rejected". | Rejection Date, Stage Reached, Feedback Notes (if provided). | System updates funnel metrics; recommends similar high-fit open roles. |
| **9. WITHDRAWN** | Candidate voluntarily exits process (e.g., accepted competing offer) `[FACT]`. | Selects "Withdraw". | Withdrawal Reason. | Closes active card cleanly. |

---

## 3. Persistent Job Snapshot Schema (Zero Context Loss)

When a job is saved or moved to `PRIORITIZED`, the system generates an immutable local snapshot to protect the candidate against broken/expired job links:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   PERSISTENT JOB SNAPSHOT SCHEMA                       │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Core Metadata:                                                      │
│    • Job Title: (e.g., "Associate Data Analyst")                       │
│    • Company Name: (e.g., "Acme Analytics")                            │
│    • Original Posting URL: (Archived hyperlink)                        │
│    • Date Saved & Date Applied: (ISO Timestamps)                       │
│                                                                        │
│ 2. Extracted Job Context:                                              │
│    • Full JD Text Snapshot: (Permanent immutable text archive)         │
│    • Requirement Tiers: (Core Prerequisites vs. Preferred Tools)       │
│                                                                        │
│ 3. Match Intelligence:                                                 │
│    • Fit Qualitative Tier: (Strong Fit / Stretch / Low Match)          │
│    • Key Highlighted Strengths: (Top 3 candidate project citations)    │
│    • Identified Gaps & Advice: (Learnable gaps & framing notes)        │
│                                                                        │
│ 4. Candidate Interaction Context:                                      │
│    • Custom Notes & Reminders: (e.g., "Referred by alum on LinkedIn")   │
│    • Current Pipeline Status: (Kanban Stage)                           │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 4. Interaction Model: Kanban vs. Focused List

* **Default View (Focused Pipeline / Kanban)**:
  * Horizontal stage columns for active states (`Prioritized` ➔ `Applied` ➔ `Screening` ➔ `Interview`).
  * Each card displays: **Company Name**, **Role Title**, **Fit Tier Tag (e.g., Strong Fit)**, and **Days in Stage**.
* **1-Click Slide-Out Drawer**:
  * Clicking any card opens a slide-over panel displaying the **Complete Saved Job Snapshot** and **Interview Cheat Sheet** without navigating away from the pipeline.
* **Archived / Inactive Filter**:
  * `Rejected` and `Withdrawn` cards are tucked into an expandable archive tab to keep the active board clean and psychologically motivating `[ASSUMPTION]`.
