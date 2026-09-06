# Product Metric Definitions & Specification

This document provides formal operational definitions, mathematical formulas, telemetry event sources, and decision rationales for all metrics in **AI Career Copilot**.

---

## 1. Metric Dictionary by Category

### 1.1 Activation Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-ACT-01** | **Profile Activation Rate (PAR)** | % of signed-up users who successfully upload and verify their candidate profile baseline. | $\frac{\text{profile\_ready}}{\text{signup\_completed}} \times 100$ | `profile_created`, `profile_ready` | Indicates onboarding friction; tests resume parsing speed. |
| **M-ACT-02** | **First Job Ingestion Rate (FJIR)** | % of activated profiles that ingest at least 1 job description within their first session. | $\frac{\text{first\_jd\_ingested}}{\text{profile\_ready}} \times 100$ | `profile_ready`, `jd_ingested` | Measures immediate user momentum and top-of-funnel conversion. |
| **M-ACT-03** | **Time-to-First-Decision (TTFD)** | Median time in minutes from initial signup to the candidate's first high-confidence decision. | $\text{Median}(T_{\text{first\_decision}} - T_{\text{signup}})$ | `signup_completed`, `decision_committed` | Measures time-to-value velocity (<5 mins target) `[DESIGN TARGET]`. |

---

### 1.2 Decision Velocity & Efficiency Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-EFF-01** | **Median Time-to-Decision (TTD)** | Dwell time from successful JD ingestion to triage execution (Queue, Save, or Discard). | $\text{Median}(T_{\text{decision\_committed}} - T_{\text{jd\_ingested}})$ | `jd_ingested`, `decision_committed` | Measures reduction in evaluation cognitive load (<90s target) `[DESIGN TARGET]`. |
| **M-EFF-02** | **Analysis Completion Rate (ACR)** | % of started fit analyses that render the complete explanation without abandonment. | $\frac{\text{fit\_analysis\_completed}}{\text{fit\_analysis\_started}} \times 100$ | `fit_analysis_started`, `fit_analysis_completed` | Identifies client-side timeouts or API extraction drops. |
| **M-EFF-03** | **Triage Conversion Velocity (TCV)** | % of completed analyses that result in an explicit triage decision in <180s. | $\frac{\text{decisions\_under\_180s}}{\text{total\_fit\_analyses\_completed}} \times 100$ | `fit_analysis_completed`, `decision_committed` | Measures effectiveness of the explainable UI in driving decisive action. |

---

### 1.3 Decision Quality & Explainability Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-DEC-01** | **High-Fit Acceptance Rate (HFAR)** | % of roles classified as *Strong Fit* that the user moves to Tier 1 Priority Queue. | $\frac{\text{strong\_fit\_prioritized}}{\text{total\_strong\_fit\_recommended}} \times 100$ | `fit_tier_rendered`, `priority_accepted` | Measures user alignment and trust in high-conviction recommendations. |
| **M-DEC-02** | **Stretch Opportunity Viability Rate** | % of *Stretch* recommendations that the user accepts with documented gap-learning notes. | $\frac{\text{stretch\_roles\_queued}}{\text{total\_stretch\_recommended}} \times 100$ | `fit_tier_rendered`, `priority_accepted` | Validates whether gap severity breakdown reduces candidate imposter anxiety. |
| **M-DEC-03** | **Deliberate Discard Ratio (DDR)** | % of *Low Fit* or *Blocker Gap* roles explicitly discarded by candidate. | $\frac{\text{low\_fit\_discarded}}{\text{total\_low\_fit\_recommended}} \times 100$ | `fit_tier_rendered`, `decision_committed` | Measures hours saved from avoiding dead-end applications `[PRODUCT INFERENCE]`. |

---

### 1.4 Trust & Auditability Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-TRS-01** | **Evidence Inspection Rate (EIR)** | % of analyzed roles where candidate expands/hovers over at least 1 evidence citation tooltip. | $\frac{\text{analyses\_with\_evidence\_click}}{\text{total\_analyses\_completed}} \times 100$ | `fit_analysis_completed`, `evidence_inspected` | Measures candidate demand for explainability and auditability. |
| **M-TRS-02** | **AI Hallucination Correction Rate** | % of extracted requirements where user edits or flags an AI-inferred skill match. | $\frac{\text{skills\_edited\_or\_flagged}}{\text{total\_skills\_extracted}} \times 100$ | `ai_evidence_corrected` | Core AI quality indicator; triggers prompt ontology tuning. |
| **M-TRS-03** | **Ambiguity Alert Heed Rate (AAHR)**| % of *Low-Signal JD* warnings where candidate manually reviews raw text before deciding. | $\frac{\text{ambiguous\_jds\_audited}}{\text{total\_ambiguity\_warnings}} \times 100$ | `ambiguity_warning_shown`, `raw_jd_viewed` | Evaluates whether candidates heed system uncertainty signals. |

---

### 1.5 Prioritization & Queue Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-PRI-01** | **Queue Execution Rate (QER)** | % of Prioritized Tier 1 roles that are marked as "Applied" within 7 days. | $\frac{\text{tier\_1\_applied\_7d}}{\text{total\_tier\_1\_prioritized}} \times 100$ | `priority_accepted`, `status_changed_applied` | Validates whether prioritization successfully drives focused application sprints. |
| **M-PRI-02** | **Manual Priority Override Rate (POR)**| % of opportunities where candidate manually changes the AI-recommended priority tier. | $\frac{\text{priority\_tier\_overrides}}{\text{total\_prioritizations}} \times 100$ | `priority_overridden` | Measures divergence between AI ranking heuristic and user preference. |

---

### 1.6 Application Tracking & Context Archival Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-TRK-01** | **Snapshot Persistence Rate (SPR)** | % of saved jobs that create an immutable local snapshot containing complete JD text. | $\frac{\text{successful\_snapshots\_created}}{\text{total\_jobs\_saved}} \times 100$ | `job_saved`, `snapshot_persisted` | Technical integrity metric; ensures 100% data persistence. |
| **M-TRK-02** | **Interview Context Retrieval Rate (ICRR)**| % of active applications in *Screening / Interview* where the candidate opens the Interview Drawer. | $\frac{\text{context\_drawers\_opened}}{\text{active\_interview\_stages}} \times 100$ | `status_screening_interview`, `interview_context_opened` | Validates core hypothesis: snapshot retention prevents interview context loss `[HYPOTHESIS]`. |
| **M-TRK-03** | **Pipeline Update Velocity (PUV)** | Average days between candidate status updates on active pipeline cards. | $\text{Avg}(T_{\text{status\_update\_N}} - T_{\text{status\_update\_N-1}})$ | `application_status_changed` | Measures whether candidate maintains Kanban vs. spreadsheet relapse. |

---

### 1.7 Retention & User Stickiness Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-RET-01** | **Weekly Active Decision-Makers (WADM)**| Unique candidates who execute $\ge 3$ deliberate triage decisions within a 7-day window. | $\text{Count}(\text{Users with W-HCCD} \ge 3)$ | `decision_committed` | Core retention metric; tracks active early-career job hunters. |
| **M-RET-02** | **Search-Cycle Cohort Retention** | % of activated users in week $W_0$ who return and execute $\ge 1$ decision in week $W_3$. | $\frac{\text{active\_users\_W3}}{\text{activated\_cohort\_W0}} \times 100$ | `session_started`, `decision_committed` | Measures longitudinal workflow stickiness across full hiring cycle. |

---

### 1.8 AI Quality & Grounding Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-AI-01** | **Unsupported Evidence Rate (UER)** | % of generated match claims flagged or identified as missing from raw profile text. | $\frac{\text{unsupported\_claims\_flagged}}{\text{total\_match\_claims\_generated}} \times 100$ | `ai_evidence_flagged` | **Critical AI Safety Guardrail**: Must remain <1.0% `[VALIDATION REQUIRED]`. |
| **M-AI-02** | **Requirement Extraction Accuracy** | % of extracted technical entities validated as accurate vs. boilerplate noise in audit samples. | $\frac{\text{valid\_technical\_entities}}{\text{total\_extracted\_entities}} \times 100$ | `jd_audit_logged` | Measures prompt taxonomy fidelity across diverse corporate JDs. |
| **M-AI-03** | **Insufficient Info Detection Rate** | % of brief (<50 words) or fluff-heavy JDs correctly flagged as *Insufficient Information*. | $\frac{\text{vague\_jds\_flagged}}{\text{total\_vague\_jds\_ingested}} \times 100$ | `ambiguity_detected` | Prevents hallucinations on empty/marketing job postings. |

---

### 1.9 System Performance & Reliability Metrics
| Metric ID | Metric Name | Definition | Formula | Telemetry Event Source | Strategic Decision Inferred |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **M-REL-01** | **Resume Parse Latency (p95)** | 95th percentile latency in seconds for extracting structured profile from PDF resume. | $\text{p95}(T_{\text{parse\_end}} - T_{\text{upload\_start}})$ | `resume_uploaded`, `resume_parsed` | Target <5.0 seconds `[DESIGN TARGET]`. |
| **M-REL-02** | **Fit Evaluation Latency (p95)** | 95th percentile latency in seconds for generating complete explainable fit breakdown. | $\text{p95}(T_{\text{fit\_rendered}} - T_{\text{fit\_started}})$ | `fit_analysis_started`, `fit_analysis_completed` | Target <3.0 seconds `[DESIGN TARGET]`. |
| **M-REL-03** | **Ingestion Error Rate (IER)** | % of raw text or URL ingestion attempts that result in an unhandled system crash or parse failure. | $\frac{\text{ingestion\_errors}}{\text{total\_ingestions}} \times 100$ | `jd_ingest_failed`, `jd_ingested` | Target <1.0% failure `[DESIGN TARGET]`. |

---

## 2. Metric Traceability Matrix

| Problem / Pain Point | Related JTBD | Product Capability | Primary Metric Monitored | Strategic Value / Why It Matters |
| :--- | :--- | :--- | :--- | :--- |
| **`PP-08` Form Fatigue** | `JTBD 1` | 1-Click Resume PDF Parsing | `M-ACT-01` Profile Activation Rate | Ensures candidate reaches core value without onboarding drop-off. |
| **`PP-03` Bloated JDs** | `JTBD 1` | Requirement Entity Structuring | `M-EFF-01` Median Time-to-Decision | Reduces 30-min JD decoding to <90s structured scan. |
| **`PP-05` Opaque Match Badges**| `JTBD 1` | Explainable Fit Breakdown | `M-DEC-01` High-Fit Acceptance Rate | Eliminates guesswork and builds verified match confidence. |
| **`PP-06` Unclear Gaps** | `JTBD 3` | Categorized Gap Severity Tiers | `M-DEC-02` Stretch Viability Rate | Prevents self-disqualification on learnable secondary tools. |
| **`PP-07` Tab Paralysis** | `JTBD 2` | 3-Tier Prioritization Queue | `M-PRI-01` Queue Execution Rate | Replaces spray-and-pray with focused, high-conviction sprints. |
| **`PP-09` Expired 404 Links** | `JTBD 5` | Immutable Snapshot Archival | `M-TRK-02` Interview Context Retrieval Rate | Guarantees zero context loss when recruiters call weeks later. |
