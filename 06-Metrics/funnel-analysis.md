# Product Funnel Analysis & Conversion Architecture

This document specifies the 10-stage core user conversion funnel for **AI Career Copilot**, defining the purpose, telemetry signals, drop-off diagnostics, and corrective product interventions for each stage.

---

## 1. The 10-Stage Core Product Funnel

```
[1. Profile Created] ──▶ [2. Profile Ready] ──▶ [3. JD Ingested] ──▶ [4. JD Structured] ──▶ [5. Fit Completed]
                                                                                                 │
                                                                                                 ▼
[10. App Tracked] ◀── [9. Job Applied] ◀── [8. Prioritized] ◀── [7. Decision Made] ◀── [6. Evidence Reviewed]
```

---

## 2. Stage-by-Stage Funnel Diagnostics

| Stage # | Stage Name | Stage Purpose & User Milestone | Conversion Metric Measured | Key Drop-Off Signal | Potential Product Problem | Recommended Product Action |
| :-: | :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | **Profile Created** | Candidate enters onboarding drop zone. | `Signups Initiated` | Immediate bounce before upload. | Value proposition unclear on welcome screen. | Emphasize "Analyze a Job in 60s" teaser; provide sample demo job `[PRODUCT INFERENCE]`. |
| **2** | **Profile Ready** | Candidate confirms extracted skills/projects. | $\frac{\text{Profile Ready}}{\text{Profile Created}}$ | Abandonment on profile verification view. | Parser generated messy text or failed on unstructured PDF. | Add 1-click popular skill chips; simplify project editing fields. |
| **3** | **JD Ingested** | Candidate inputs job text or URL. | $\frac{\text{First JD Ingested}}{\text{Profile Ready}}$ | User activates profile but never pastes a job. | User has no active job listings at hand. | Provide pre-loaded entry-level sample postings for instant evaluation. |
| **4** | **JD Structured** | System segments requirements into entity tiers. | $\frac{\text{JD Structured}}{\text{JD Ingested}}$ | Parsing error or unhandled format crash. | Scraper blocked by URL login wall or text <50 words. | Surface prominent "Paste Raw Text" fallback immediately upon URL error. |
| **5** | **Fit Completed** | System renders explainable fit breakdown. | $\frac{\text{Fit Rendered}}{\text{JD Structured}}$ | High latency spinner (>10s) or API timeout. | LLM prompt timeout or latency spike. | Stream partial tokens; render skeleton cards with progress checklist. |
| **6** | **Evidence Reviewed**| Candidate inspects match citations & gaps. | $\frac{\text{Evidence Inspected}}{\text{Fit Completed}}$ | Dwell time <5s with zero tooltip clicks. | UI looks like a black-box percentage score; text too dense. | Use prominent color-coded badges and clear "Why You Match" accordion tags. |
| **7** | **Decision Made** | Candidate commits triage action (Queue/Discard). | $\frac{\text{Decisions Committed}}{\text{Fit Completed}}$ | Dwell time >180s followed by tab closure. | Decision paralysis; ambiguous recommendation tier. | Clearly highlight single recommended action (e.g. *"Apply: 3 Core Matches Verified"*). |
| **8** | **Prioritized** | Role assigned to Tier 1 Target or Tier 2 Stretch. | $\frac{\text{Roles Prioritized}}{\text{Decisions Committed}}$ | Roles reviewed but never committed to queue. | Candidate doubts personal ability or fears applying. | Reassure on learnable gaps; surface 1-click "Add to High-Fit Target". |
| **9** | **Job Applied** | Candidate submits application on employer site. | $\frac{\text{Marked Applied}}{\text{Prioritized (7-Day)}}$ | Roles sit in Tier 1 queue without submission. | Complex external ATS application portal (e.g. 10-page Workday). | Provide interview cheat sheet cues to speed up external submission. |
| **10**| **App Tracked** | Candidate logs stage progression in Kanban. | $\frac{\text{Status Updates}}{\text{Total Applied Cards}}$ | Cards remain static in "Applied" forever. | Candidate forgets to update status or lost interest. | Send weekly email digest: *"Update status on 3 pending applications"*. |

---

## 3. High-Priority Drop-off Diagnostic Framework

To pinpoint product friction without guessing, the team monitors three critical drop-off ratios:

### Diagnostic Ratio 1: Onboarding Friction Ratio (OFR)
$$\text{OFR} = \frac{\text{profile\_created} - \text{profile\_ready}}{\text{profile\_created}}$$
* **Diagnostic Meaning**: A high OFR (>20%) indicates that resume parsing failed, extracted bad data, or presented an overwhelming manual verification form `[PRODUCT INFERENCE]`.

### Diagnostic Ratio 2: Cognitive Paralysis Ratio (CPR)
$$\text{CPR} = \frac{\text{fit\_analysis\_completed} - \text{decision\_committed}}{\text{fit\_analysis\_completed}}$$
* **Diagnostic Meaning**: A high CPR (>35%) indicates the explainable fit card was too confusing, ambiguous, or failed to give the candidate sufficient conviction to either queue or discard the opportunity `[PRODUCT INFERENCE]`.

### Diagnostic Ratio 3: Queue Abandonment Ratio (QAR)
$$\text{QAR} = \frac{\text{tier\_1\_prioritized} - \text{marked\_as\_applied\_7d}}{\text{tier\_1\_prioritized}}$$
* **Diagnostic Meaning**: A high QAR (>40%) indicates candidates are prioritizing opportunities but failing to overcome the friction of applying on external company portals `[PRODUCT INFERENCE]`.
