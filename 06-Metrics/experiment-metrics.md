# Experimentation Framework & Metric Plans

This document outlines four candidate A/B and multivariate experiments designed to validate core product hypotheses in future releases of **AI Career Copilot**.

> **Note**: These experiments are future research specifications. No results or user samples are claimed as completed `[HYPOTHESIS]`.

---

## 1. Experiment Overview Matrix

| Exp ID | Experiment Name | Core Hypothesis Tested | Primary Evaluation Metric | Primary Guardrail |
| :---: | :--- | :--- | :--- | :--- |
| **EXP-A** | **Qualitative Tiers vs. Numerical Scores** | Qualitative tiers produce higher decision conviction than percentage scores `[HYPOTHESIS]`. | **Decision Conviction Rate (DCR)**: % of reviews ending in committed triage. | **False Confidence Override Rate** (<5%). |
| **EXP-B** | **Evidence-First vs. Summary-First UI** | Leading with inspectable citations increases user trust in AI output `[HYPOTHESIS]`. | **Evidence Inspection Rate (EIR)** + **Triage Velocity**. | **Median Time-to-Decision** (<120s). |
| **EXP-C** | **Raw JD Paste vs. URL Ingestion Focus** | Emphasizing raw text paste minimizes first-session drop-off vs. URL scraping `[HYPOTHESIS]`. | **First Ingestion Completion Rate (FICR)**. | **Session Ingestion Friction Rating**. |
| **EXP-D** | **Auto-Queue vs. Guided Manual Priority** | Requiring explicit candidate confirmation increases application follow-through `[HYPOTHESIS]`. | **7-Day Queue Execution Rate (QER)**. | **Pipeline Inactive Ratio**. |

---

## 2. Detailed Experiment Specifications

### Experiment EXP-A: Qualitative Fit Tiers vs. Single Percentage Score

* **Hypothesis**: Presenting candidate fit as qualitative tiers (*Strong Fit*, *Stretch*, *Low Fit*) will increase candidate application conviction and reduce decision hesitation compared to a single percentage match score (e.g., "78% Match") `[HYPOTHESIS]`.
* **Variants**:
  * **Control (A)**: Displays a circular numerical match percentage (e.g., "82% Match") alongside standard skill tags.
  * **Variant (B)**: Displays 5 qualitative assessment tiers (*Strong Fit*, *Reasonable Fit*, *Stretch*, *Low Fit*, *Insufficient Info*) with 3-bucket requirement breakdown.
* **Primary Metric**: **Decision Conviction Rate (DCR)** — % of viewed analyses that result in a deliberate triage action (Queue or Discard).
* **Secondary Metrics**: Median dwell time before decision; % of stretch roles queued.
* **Guardrail Metric**: User-reported mismatch rate (must not increase by >2%).
* **Decision Rule**: Roll out Variant B if DCR increases by $\ge 10\%$ with no statistically significant increase in user-reported mismatches `[HYPOTHESIS]`.
* **What We Learn**: Proves whether early-career candidates benefit more from qualitative reasoning than arbitrary mathematical pseudo-precision.

---

### Experiment EXP-B: Evidence-First vs. Summary-First UI Architecture

* **Hypothesis**: Displaying verified resume project citations directly adjacent to extracted requirements will increase candidate confidence compared to rendering a high-level narrative summary first `[HYPOTHESIS]`.
* **Variants**:
  * **Control (A - Summary First)**: Shows a 3-bullet AI narrative summary at the top; requirement evidence is tucked inside collapsed accordions below.
  * **Variant (B - Evidence First)**: Displays the 3-bucket requirement breakdown with inline project citations front-and-center; narrative summary is secondary.
* **Primary Metric**: **Evidence Inspection Rate (EIR)** — % of users engaging with underlying citations.
* **Secondary Metrics**: Time-to-Decision (TTD); return cohort retention.
* **Guardrail Metric**: Total cognitive review time must not exceed 120 seconds.
* **Decision Rule**: Adopt Variant B if EIR increases by $\ge 20\%$ and TTD remains under 90 seconds.
* **What We Learn**: Identifies whether users treat the tool as an audit engine (evidence-seeking) or a high-level summarizer.

---

### Experiment EXP-C: Raw Text Ingestion vs. URL Scraper Prominence

* **Hypothesis**: Positioning the 1-click Raw Text Paste box as the default active tab will yield higher ingestion completion rates than defaulting to the URL scraper input `[HYPOTHESIS]`.
* **Variants**:
  * **Control (A - URL Default)**: Default view opens with URL input field; "Paste Text" is a secondary tab.
  * **Variant (B - Paste Default)**: Default view opens with raw text paste area with sample button; "URL Ingestion" is a secondary tab.
* **Primary Metric**: **First Ingestion Completion Rate (FICR)** — % of activated profiles that successfully structure a JD in session 1.
* **Secondary Metrics**: Ingestion error rate (scraping failures).
* **Guardrail Metric**: Overall ingestion satisfaction score.
* **Decision Rule**: Adopt Variant B if FICR is $\ge 15\%$ higher due to bypassing login walls on LinkedIn/Handshake.
* **What We Learn**: Measures whether external platform authentication walls create severe friction for early-career job hunters.

---

### Experiment EXP-D: Automatic Prioritization vs. Guided User Confirmation

* **Hypothesis**: Requiring candidates to actively confirm their priority tier before adding to queue will increase downstream application completion compared to automatically filing jobs into tiers `[HYPOTHESIS]`.
* **Variants**:
  * **Control (A - Auto-Queue)**: System automatically inserts evaluated jobs into Kanban columns upon analysis.
  * **Variant (B - Guided Confirmation)**: System recommends a tier, but candidate must click "Add to High-Fit Targets" to commit the card.
* **Primary Metric**: **Queue Execution Rate (QER)** — % of queued roles submitted on employer sites within 7 days.
* **Secondary Metrics**: Pipeline board clutter ratio; candidate return rate.
* **Guardrail Metric**: Zero-action abandonment rate on analysis card.
* **Decision Rule**: Adopt Variant B if 7-day application conversion increases by $\ge 25\%$, confirming that active candidate agency drives higher follow-through.
* **What We Learn**: Proves whether user agency creates psychological ownership over the job hunt compared to passive automation.
