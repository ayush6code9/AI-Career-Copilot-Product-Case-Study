# Event Instrumentation Taxonomy & Privacy Schema

This document defines the client-side and server-side telemetry events instrumented in **AI Career Copilot**, detailing event triggers, property schemas, and strict privacy boundaries.

---

## 1. Privacy & Responsible Telemetry Guardrails

> **Core Privacy Rule**: Telemetry captures *interaction metadata and quality signals*, NEVER sensitive Personally Identifiable Information (PII), raw resume text, or employer proprietary contact details `[FACT]`.

```
┌────────────────────────────────────────────────────────────────────────┐
│                        TELEMETRY PRIVACY FILTER                        │
├──────────────────────────────────┬─────────────────────────────────────┤
│ ALLOWED IN TELEMETRY             │ STRICTLY PROHIBITED IN TELEMETRY    │
├──────────────────────────────────┼─────────────────────────────────────┤
│ • Anonymous Session / User UUIDs │ • Candidate Full Name & Email       │
│ • Role Category (e.g. DataAnalyst│ • Phone Numbers & Home Addresses    │
│ • Extracted Skill Count & Types  │ • Full Raw Resume Text Body         │
│ • Qualitative Tier (Strong/Stretch)• Full Raw Job Description Text     │
│ • Dwell Times & Latencies        │ • Private Recruiter Email Addresses │
│ • Error Codes & Success Flags    │ • Offer Compensation Specifics      │
└──────────────────────────────────┴─────────────────────────────────────┘
```

---

## 2. Standard Event Properties (Attached to All Events)

Every dispatched event automatically inherits standard environment context:
* `user_id`: Anonymous UUID (persisted in local session storage).
* `session_id`: Unique session UUID.
* `timestamp`: ISO-8601 UTC timestamp.
* `client_platform`: Web / Desktop / Mobile.
* `app_version`: SemVer string (e.g., `1.0.0-mvp`).

---

## 3. Product Event Taxonomy Table

| Event Name | User / System Trigger | Specific Event Properties | Purpose / Strategic Insight |
| :--- | :--- | :--- | :--- |
| **`profile_created`** | User initiates account/profile setup. | `source`: ("resume_upload" \| "text_paste") | Tracks onboarding top-of-funnel entry. |
| **`resume_uploaded`** | PDF/DOCX file uploaded to drop zone. | `file_format`: ("pdf" \| "docx"), `file_size_kb`: Integer | Monitors upload file format distribution. |
| **`resume_parsed`** | Resume parser finishes extraction. | `latency_ms`: Integer, `skills_extracted_count`: Integer, `projects_extracted_count`: Integer, `status`: ("success" \| "error") | Measures parsing speed and extraction yield. |
| **`profile_ready`** | User reviews and confirms profile. | `target_roles_selected`: Array[String], `manual_edits_count`: Integer | Key activation milestone; measures manual correction effort. |
| **`jd_ingested`** | Raw text or URL submitted for analysis. | `ingest_mode`: ("raw_text" \| "url"), `text_length_chars`: Integer, `url_domain`: String | Tracks ingestion mode split (Paste vs. URL). |
| **`jd_parsed`** | JD entity structuring completes. | `latency_ms`: Integer, `hard_reqs_count`: Integer, `preferred_reqs_count`: Integer, `is_ambiguous`: Boolean | Evaluates JD complexity and ambiguity flag rate. |
| **`fit_analysis_started`** | User clicks "Analyze Opportunity Fit". | `job_id`: UUID, `target_role_category`: String | Tracks fit evaluation demand per role type. |
| **`fit_analysis_completed`**| Explainable fit breakdown rendered. | `latency_ms`: Integer, `qualitative_tier`: ("strong_fit" \| "reasonable_fit" \| "stretch" \| "low_fit" \| "insufficient_info"), `matched_skills_count`: Integer, `gaps_count`: Integer | Core AI output event; tracks qualitative tier distribution. |
| **`evidence_inspected`** | User hovers/clicks an evidence tooltip. | `skill_name`: String, `match_type`: ("demonstrated" \| "transferable"), `dwell_time_ms`: Integer | Measures trust engagement with explainability reasoning. |
| **`gap_details_viewed`** | User expands gap severity breakdown. | `gap_severity`: ("blocking" \| "important" \| "learnable" \| "nice_to_have"), `skill_name`: String | Evaluates whether candidates inspect learnable gap advice. |
| **`ambiguity_warning_shown`**| Amber warning rendered on low-signal JD.| `jd_id`: UUID, `confidence_score`: Float | Monitors frequency of vague, fluff-heavy job descriptions. |
| **`decision_committed`** | User executes explicit triage action. | `decision_type`: ("prioritized" \| "saved" \| "discarded"), `dwell_before_decision_s`: Integer, `assigned_tier`: ("tier_1" \| "tier_2" \| "tier_3" \| "discard") | **Core North Star Event (W-HCCD)**; measures decision velocity and conviction. |
| **`priority_overridden`** | User manually drags card to change tier.| `from_tier`: String, `to_tier`: String, `role_category`: String | Measures divergence between AI ranking heuristic and user judgment. |
| **`job_saved`** | Job card committed to tracking pipeline. | `initial_status`: ("saved" \| "prioritized"), `snapshot_size_kb`: Integer | Confirms permanent local snapshot creation. |
| **`application_status_changed`**| Card moved to new Kanban stage. | `from_stage`: String, `to_stage`: ("applied" \| "screening" \| "interview" \| "offer" \| "rejected"), `days_in_previous_stage`: Integer | Tracks candidate progression across the real hiring funnel. |
| **`interview_context_opened`**| Slide-out interview drawer opened. | `job_id`: UUID, `stage`: ("screening" \| "interview"), `dwell_time_s`: Integer | Validates context retention during recruiter screening calls. |
| **`ai_evidence_corrected`** | User flags or edits an AI-matched skill. | `skill_name`: String, `correction_type`: ("removed_match" \| "added_skill" \| "reclassified_gap") | **Critical AI Safety Signal**: Direct feedback for prompt calibration. |

---

## 4. Sampling & Transmission Strategy

* **Critical Flow Events (100% Sampling)**: `profile_ready`, `decision_committed`, `application_status_changed`, `ai_evidence_corrected`.
* **Diagnostic Events (Batched & Debounced)**: `evidence_inspected` (debounced by 300ms to ignore rapid mouse movements), `gap_details_viewed`.
* **Local Storage Cache**: Events are queued locally in browser `IndexedDB` / `localStorage` and flushed in batches every 30 seconds or upon page visibility change to minimize network overhead `[PRODUCT INFERENCE]`.
