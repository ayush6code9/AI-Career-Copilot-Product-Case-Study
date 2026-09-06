# Technical & Functional Dependency Map

This document establishes the topological sequencing, critical path, and structural dependency hierarchy across all backlog capabilities in **AI Career Copilot**.

---

## 1. Topological Dependency Architecture

```
┌─────────────────────────────────┐       ┌─────────────────────────────────┐
│           STAGE 1:              │       │           STAGE 1:              │
│    CANDIDATE PROFILE BASELINE   │       │      JOB INGESTION & DISCOVERY  │
│                                 │       │                                 │
│ [FB-CP-01] Resume PDF Parsing   │       │ [FB-JD-01] Raw JD Text Paste    │
│            │                    │       │            │                    │
│            ▼                    │       │            ▼                    │
│ [FB-CP-02] Manual Skill Editor  │       │ [FB-PS-01] Requirement Parsing │
└────────────────┬────────────────┘       └────────────────┬────────────────┘
                 │                                         │
                 └────────────────────┬────────────────────┘
                                      ▼
                        ┌───────────────────────────┐
                        │         STAGE 2:          │
                        │     CORE FIT ANALYSIS     │
                        │                           │
                        │ [FB-FA-01] Alignment Engine│
                        │            │              │
                        │            ▼              │
                        │ [FB-FA-02] Qualitative Tiers
                        │ [FB-FA-03] Evidence Tooltips
                        │ [FB-FA-04] Gap Severity   │
                        └─────────────┬─────────────┘
                                      │
                 ┌────────────────────┴────────────────────┐
                 ▼                                         ▼
   ┌───────────────────────────┐             ┌───────────────────────────┐
   │         STAGE 3A:         │             │         STAGE 3B:         │
   │ OPPORTUNITY PRIORITIZATION│             │    APPLICATION TRACKING   │
   │                           │             │                           │
   │ [FB-PR-01] 3-Tier Queue   │             │ [FB-TR-01] Snapshot Save  │
   │            │              │             │            │              │
   │            ▼              │             │            ▼              │
   │ [FB-PR-02] Tier Overrides │             │ [FB-TR-02] Kanban Pipeline│
   │ [FB-PR-03] Role Filters   │             │ [FB-TR-03] Context Drawer │
   └───────────────────────────┘             └───────────────────────────┘
```

---

## 2. Dependency Categorization Matrix

### 2.1 Hard Dependencies (Strict Architectural Blockers)
Capabilities that cannot function or be tested without their upstream prerequisites:

| Downstream Capability | Blocked By (Hard Dependency) | Architectural Rationale |
| :--- | :--- | :--- |
| **FB-FA-01 (Fit Alignment Engine)** | `FB-CP-02` (Verified Profile) & `FB-PS-01` (Structured JD) | Semantic comparison requires both candidate evidence entities and structured JD criteria `[FACT]`. |
| **FB-FA-02 (Qualitative Tiers)** | `FB-FA-01` (Fit Alignment Engine) | Qualitative tiering is synthesized directly from the multi-dimensional alignment matrix `[PRODUCT INFERENCE]`. |
| **FB-FA-03 (Evidence Tooltips)** | `FB-FA-01` (Fit Alignment Engine) | Tooltips render the exact candidate profile citations mapped during alignment analysis `[PRODUCT INFERENCE]`. |
| **FB-FA-04 (Gap Severity Tiers)** | `FB-FA-01` (Fit Alignment Engine) | Missing requirements must first be identified before they can be segmented by severity `[PRODUCT INFERENCE]`. |
| **FB-PR-01 (Prioritization Queue)** | `FB-FA-02` (Qualitative Fit Tiers) | Queue sorting relies on the qualitative fit tier output (Strong Fit vs. Stretch) `[PRODUCT INFERENCE]`. |
| **FB-TR-01 (Snapshot Archival)** | `FB-FA-01` (Fit Analysis) & `FB-JD-01` (Raw JD) | Snapshot persists the parsed JD text alongside the evaluated match breakdown `[FACT]`. |
| **FB-TR-02 (Kanban Pipeline Board)**| `FB-TR-01` (Snapshot Archival) | Pipeline cards represent persisted job snapshots transitioning through status stages `[FACT]`. |

---

### 2.2 Soft Dependencies (Functional Enhancers)
Capabilities that function independently but deliver significantly higher user value when paired with upstream features:

| Capability | Enhanced By (Soft Dependency) | User Experience Enhancement |
| :--- | :--- | :--- |
| **FB-PR-01 (Prioritization Queue)** | `FB-CP-03` (Target Role Preferences) | Calibrates queue sorting using candidate role goals in addition to raw technical overlap `[PRODUCT INFERENCE]`. |
| **FB-TR-03 (Interview Context Drawer)**| `FB-FA-05` (Actionable Recommendation Cues) | Enriches the interview drawer with tailored talking points and project framing notes `[PRODUCT INFERENCE]`. |
| **FB-JD-02 (URL Ingestion)** | `FB-PS-02` (Ambiguity Warning Alerts) | Scraped URLs often contain noisy headers; ambiguity alerts guide user when scraping quality is low `[PRODUCT INFERENCE]`. |

---

### 2.3 Independent Capabilities (Zero Dependencies)
Features that can be developed and validated in isolation:
* **`FB-JD-01` (Raw JD Text Ingestion)**: Simple multi-line text input container.
* **`FB-CP-01` (Resume PDF Parsing)**: Standalone document text and entity extraction engine.
* **`FB-CP-03` (Target Role Preference Selector)**: Standalone preference pill selection UI.

---

## 3. Critical Path Analysis (MVP Release Sequence)

To minimize delivery risk and unlock parallel workflows, development should execute along the **Critical Path**:

```
[SPRINT 1: Foundational Ingestion & Profile Engine]
Step 1: Build FB-JD-01 (Raw JD Text Ingestion) & FB-PS-01 (Requirement Structuring)
Step 2: Build FB-CP-01 (Resume PDF Parser) & FB-CP-02 (Manual Profile Verification)

[SPRINT 2: Core Value Engine (Explainable Fit)]
Step 3: Build FB-FA-01 (Fit Alignment Engine)
Step 4: Build FB-FA-02 (Qualitative Tiers), FB-FA-03 (Evidence Tooltips), FB-FA-04 (Gap Severity)

[SPRINT 3: Decision & Execution Enablers]
Step 5: Build FB-PR-01 (3-Tier Opportunity Queue)
Step 6: Build FB-TR-01 (Snapshot Archival) & FB-TR-02 (Kanban Tracking Pipeline)

[SPRINT 4: Usability Polish & Trust Enhancers]
Step 7: Build FB-JD-02 (URL Ingestion) & FB-TR-03 (Interview Context Drawer)
```

---

## 4. Key Takeaways for Engineering Handoff

1. **Unblock Fit Engine First**: The Fit Engine (`FB-FA-01`) is the central nexus. All engineering efforts in Sprint 1 must focus on delivering clean entity outputs from `FB-CP-02` and `FB-PS-01`.
2. **Decouple URL Ingestion**: Do not block the MVP on complex URL scraping (`FB-JD-02`). Raw text ingestion (`FB-JD-01`) provides 100% functional coverage for the entire critical path `[PRODUCT INFERENCE]`.
