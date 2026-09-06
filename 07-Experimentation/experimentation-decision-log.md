# Experimentation Decision Log

This document records the foundational research decisions, testing methodologies, alternative evaluations, and revisit triggers for validating **AI Career Copilot**.

---

## 1. Decision Log Architecture

```
┌────────────────────────────────────────────────────────────────────────┐
│                    EXPERIMENTATION DECISION LOG                        │
├────────────────────────────────────────────────────────────────────────┤
│ ED-01: Qualitative Tiers Must Be Formally Tested Against % Scores      │
│ ED-02: Grounded Evidence Citations Require Dedicated Trust Testing     │
│ ED-03: Raw Text Ingestion Must Be Validated as Primary Reliability Base│
│ ED-04: Automated Prioritization Must Test User Agency & Overrides     │
│ ED-05: End-to-End Workflow Must Be Validated Against Status Quo Stack  │
│ ED-06: AI Grounding Fidelity Mandated as a Hard Launch Gate            │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Structured Decision Records

### Decision ED-01: Qualitative Tiers Must Be Formally Tested Against Percentage Scores
* **Context**: While our product strategy strongly favors qualitative tiers (*Strong Fit*, *Stretch*, *Low Fit*) to eliminate pseudo-precision, numerical percentage scores (e.g., "82% Match") are deeply entrenched across legacy recruitment platforms.
* **Alternatives Considered**:
  * *Option A*: Assume qualitative tiers are permanently superior without empirical testing.
  * *Option B*: Formally design an A/B test (`EXP-01`) comparing qualitative tiers vs. numerical percentage scores.
* **Evaluation**: Assuming superiority without validation risks ignoring candidates who may demand numerical rankings for fast sorting `[PRODUCT INFERENCE]`.
* **Decision**: **Mandate Formal A/B Testing of Qualitative Tiers (`EXP-01`) (Option B).**
* **Rationale**: Validating that qualitative tiers produce higher Decision Conviction Rates and lower hesitation time provides undeniable empirical proof of our core UX differentiation `[HYPOTHESIS]`.
* **Consequence**: The codebase must support both rendering modes behind feature flags during Stage 5 testing.
* **Revisit Trigger**: If Variant A (numerical scores) achieves $\ge 20\%$ higher decision velocity without increasing application error rates, test a hybrid tier-plus-score model.

---

### Decision ED-02: Grounded Evidence Citations Require Dedicated Trust Testing
* **Context**: Does displaying verified resume project citations directly adjacent to extracted requirements actually increase user trust, or does it add unnecessary visual clutter?
* **Alternatives Considered**:
  * *Option A*: Render only a high-level text summary to keep the UI ultra-clean.
  * *Option B*: Formally test an Evidence-First layout (`EXP-02`) against a Summary-First layout.
* **Evaluation**: LLMs frequently produce plausible hallucinations. Without explicit citations, candidates may suspect the AI is guessing `[FACT]`.
* **Decision**: **Execute Dedicated Evidence-First Testing (`EXP-02`) (Option B).**
* **Rationale**: Trust in AI career recommendations is fragile. Proving that candidates actively inspect evidence tooltips validates our investment in fine-grained citation extraction `[PRODUCT INFERENCE]`.
* **Consequence**: Requires tracking tooltip hover dwell time and citation inspection telemetry.
* **Revisit Trigger**: If Evidence Inspection Rate is $<10\%$, simplify tooltips to inline tags to reduce cognitive overhead.

---

### Decision ED-03: Raw JD Ingestion Must Be Validated as the Reliability Fallback
* **Context**: Should the product mandate URL scraping or validate that raw text pasting is the superior entry point for early-career portals?
* **Alternatives Considered**:
  * *Option A*: Launch URL-only ingestion to look like modern automated tools.
  * *Option B*: Test Raw Text Ingestion vs. URL Ingestion (`EXP-03`) to measure real-world failure rates on login-walled sites.
* **Evaluation**: URL scrapers frequently fail on LinkedIn, Handshake, and Workday due to anti-bot walls `[FACT]`. Ingestion failure during onboarding causes instant candidate churn.
* **Decision**: **Validate Raw Text Paste as Primary Ingestion (`EXP-03`) (Option B).**
* **Rationale**: Proving that text paste achieves $>95\%$ completion vs. $<75\%$ for URL scraping empirically justifies our paste-first design decision `[HYPOTHESIS]`.
* **Consequence**: 1-click paste box remains the default active tab during onboarding.
* **Revisit Trigger**: Revisit URL-first prominence if automated headless proxy scrapers achieve $>95\%$ reliability across major job boards.

---

### Decision ED-04: Automated Prioritization Must Test User Agency & Overrides
* **Context**: When opportunities are automatically sorted into priority tiers, do candidates follow the recommendations or feel stripped of personal agency?
* **Alternatives Considered**:
  * *Option A*: Automatically file jobs into tiers without testing manual override behavior.
  * *Option B*: Test 3-Tier Automated Queue vs. Manual List (`EXP-04`), measuring manual override rates and 7-day application conversion.
* **Evaluation**: Full automation can induce automation bias (blindly accepting bad fits) or trigger user resistance if personal preferences are ignored `[PRODUCT INFERENCE]`.
* **Decision**: **Test Automated Prioritization with Mandatory Manual Overrides (Option B).**
* **Rationale**: Validates whether structured triage reduces decision fatigue while preserving candidate psychological ownership over their search `[PRODUCT INFERENCE]`.
* **Consequence**: Every prioritized card features 1-click drag-and-drop tier reclassification.
* **Revisit Trigger**: If override rate exceeds $35\%$, re-calibrate the underlying prioritization weighting algorithm.

---

### Decision ED-05: End-to-End Workflow Must Be Validated Against Status Quo Stack
* **Context**: Testing individual features in isolation does not prove that the consolidated copilot loop outperforms the candidate's existing tool stack.
* **Alternatives Considered**:
  * *Option A*: Measure only micro-conversions on individual screens.
  * *Option B*: Conduct an end-to-end benchmark experiment (`EXP-05`) comparing AI Career Copilot against the Status Quo stack (LinkedIn + ChatGPT + Google Sheets).
* **Evaluation**: Micro-conversions fail to capture total time saved, context retention during interviews, and holistic decision clarity `[PRODUCT INFERENCE]`.
* **Decision**: **Execute End-to-End Benchmark Experiment (`EXP-05`) (Option B).**
* **Rationale**: Proving that the consolidated decision loop cuts evaluation time by $>50\%$ while improving blocker detection accuracy validates the entire product case study `[HYPOTHESIS]`.
* **Consequence**: Requires building a standardized 10-job benchmark evaluation protocol.
* **Revisit Trigger**: If candidates perform equally fast using ad-hoc ChatGPT prompts, pivot focus toward deep workflow tracking and interview context retention.

---

### Decision ED-06: AI Grounding Fidelity Mandated as a Hard Launch Gate
* **Context**: Can a release ship if user engagement and decision velocity are high, but the AI model occasionally hallucinates candidate project evidence?
* **Alternatives Considered**:
  * *Option A*: Allow minor hallucination rates if user feedback is generally positive.
  * *Option B*: Mandate an absolute launch gate: Unsupported Evidence Rate must remain $<1.0\%$.
* **Evaluation**: If an AI tells a candidate they qualify based on a skill they do not possess, the candidate will be humiliated in a technical interview, permanently destroying brand trust `[FACT]`.
* **Decision**: **Enforce AI Grounding as an Immutable Launch Gate (Option B).**
* **Rationale**: Model safety and evidence grounding are non-negotiable prerequisites. High engagement cannot compensate for hallucinated claims `[PRODUCT INFERENCE]`.
* **Consequence**: Releases automatically fail staging validation if audit samples detect $>1.0\%$ hallucinated claims.
* **Revisit Trigger**: Non-negotiable. Permanent product standard.
