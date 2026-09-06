# UX Decisions & AI Safety Framework

This document records the foundational design trade-offs, UX rationale logs, and ethical AI safety guardrails embedded into **AI Career Copilot**.

---

## 1. UX Decision Log & Design Trade-offs

```
┌────────────────────────────────────────────────────────────────────────┐
│                        UX DECISION LOG OVERVIEW                        │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Qualitative Fit Tiers vs. Single Percentage Score                   │
│ 2. Grounded Evidence Citations vs. Summary-Only Claims                 │
│ 3. Explicit User Confirmation vs. Silent Auto-State Updates            │
│ 4. Immutable Local Snapshots vs. Dynamic Web Hyperlinks                │
│ 5. Candidate Submission Agency vs. Automated Application Bots          │
│ 6. Categorized Gap Severity vs. Binary Missing Skill Lists             │
└────────────────────────────────────────────────────────────────────────┘
```

---

### Decision 1: Qualitative Fit Tiers vs. Single Percentage Score

* **Problem**: How should overall opportunity match quality be represented to candidates without creating misleading precision or false anxiety?
* **Options Considered**:
  * *Option A (Single Score)*: Render a single prominent numerical badge (e.g., "79% Match").
  * *Option B (Qualitative Tiers)*: Render 5 structured qualitative tiers (*Strong Fit*, *Reasonable Fit*, *Stretch*, *Low Fit*, *Insufficient Info*) accompanied by multi-dimensional breakdowns.
* **Decision**: **Adopt Option B (Qualitative Tiers).**
* **Reasoning**: Numerical scores convey pseudo-precision that misleads early-career candidates `[PRODUCT INFERENCE]`. A 79% score does not inform the candidate whether the missing 21% is a fatal visa blocker or a minor 2-hour syntax tool. Qualitative tiers provide immediate strategic clarity without false precision `[ASSUMPTION]`.
* **Product Implication**: UI eliminates percentage wheels in favor of clear status badges and structured requirement columns.

---

### Decision 2: Grounded Evidence Citations vs. Summary-Only Claims

* **Problem**: How do we prevent candidate skepticism regarding AI-generated qualification matches?
* **Options Considered**:
  * *Option A*: Present high-level bulleted summaries (e.g., "Matches Python and Data Modeling").
  * *Option B*: Present explicit evidence citations linking each match directly to verified candidate resume bullets, capstones, or GitHub repos.
* **Decision**: **Adopt Option B (Grounded Evidence Citations).**
* **Reasoning**: LLMs are known for generating plausible-sounding hallucinations `[FACT]`. Grounding every match in verified candidate profile text builds absolute trust and prepares the candidate to defend their skills in interviews `[PRODUCT INFERENCE]`.
* **Product Implication**: Every green match badge includes an expandable inspectable citation tooltip.

---

### Decision 3: Explicit User Confirmation vs. Silent Background Automation

* **Problem**: Should the system automatically move roles into the application tracking pipeline upon analysis?
* **Options Considered**:
  * *Option A*: Automatically add every ingested job to the tracking board.
  * *Option B*: Require an explicit candidate action (e.g., clicking "Add to Priority Queue" or "Save to Pipeline").
* **Decision**: **Adopt Option B (Explicit User Confirmation).**
* **Reasoning**: Automatic ingestion clutters the candidate's board with low-quality, discarded roles, recreating the same disorganization found in spreadsheets `[PRODUCT INFERENCE]`. Intentional triage forces candidate focus and deliberate decision-making `[ASSUMPTION]`.
* **Product Implication**: Ingested jobs remain in a transient analysis view until the user explicitly commits them to a queue or pipeline column.

---

### Decision 4: Immutable Local Snapshots vs. Dynamic Web Hyperlinks

* **Problem**: How to prevent candidate context loss when external job postings close or change URLs?
* **Options Considered**:
  * *Option A*: Store only the external job posting URL and fetch live data when needed.
  * *Option B*: Capture and permanently store an immutable local text snapshot of the JD, parsed metadata, and match notes.
* **Decision**: **Adopt Option B (Immutable Local Snapshots).**
* **Reasoning**: Employers routinely remove or archive job postings immediately after closing applications `[FACT]`. When a recruiter calls 3 weeks later, a URL link results in a 404 error, leaving the candidate blind. Local snapshots guarantee 100% data persistence `[PRODUCT INFERENCE]`.
* **Product Implication**: All saved roles persist full JD text and match notes in local application state.

---

### Decision 5: Candidate Submission Agency vs. Automated Application Bots

* **Problem**: Should the tool attempt to automate the submission of job applications on employer portals?
* **Options Considered**:
  * *Option A*: Build automated browser-bots to fill and submit applications on external ATS platforms.
  * *Option B*: Automate JD parsing, fit evaluation, and prep notes, while routing the candidate to submit directly on the employer's official portal.
* **Decision**: **Adopt Option B (Candidate Submission Agency).**
* **Reasoning**: Mass-submission bots degrade candidate brand, trigger anti-bot ATS captchas, produce zero interview readiness, and flood corporate recruiters with low-intent spam `[DESK RESEARCH]`. Keeping submission in candidate hands reinforces quality, accountability, and high interview conversion `[PRODUCT INFERENCE]`.
* **Product Implication**: Clear CTA routing candidates directly to the official employer application URL.

---

### Decision 6: Categorized Gap Severity vs. Binary Missing Skill Lists

* **Problem**: How to present missing skills without triggering candidate imposter syndrome and unnecessary drop-off?
* **Options Considered**:
  * *Option A*: A single list titled "Missing Skills".
  * *Option B*: A 4-tier categorized gap hierarchy (**Blocking Gaps**, **Important Gaps**, **Learnable on Job**, **Nice-to-Have Preferences**).
* **Decision**: **Adopt Option B (Categorized Gap Severity).**
* **Reasoning**: Job descriptions routinely list aspirational tool stacks. Treating secondary tools as equal to mandatory degree/legal requirements causes qualified candidates to abandon applications unnecessarily `[DESK RESEARCH]`.
* **Product Implication**: Gaps are rendered with clear severity badges and tailored advice on how to address them.

---

## 2. AI-Specific UX Safety & Trust Framework

To ensure ethical, transparent, and safe AI product behavior, the application adheres to seven strict safety rules:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        AI UX SAFETY GUARDRAILS                         │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Zero Hallucination Guarantee: Never invent unstated experience.     │
│ 2. Calibrated Uncertainty: Explicitly flag vague or low-signal JDs.    │
│ 3. Strict Source Demarcation: Separate raw JD text from AI inference.  │
│ 4. No Outcome Guarantees: Never promise guaranteed interview callbacks.│
│ 5. Full Auditability: Always provide access to raw underlying data.    │
│ 6. Candidate Final Authority: AI acts as advisor; user makes decisions.│
│ 7. Privacy First: Zero data resale to third-party recruitment brokers. │
└────────────────────────────────────────────────────────────────────────┘
```

| # | Safety Rule | Operational UX Implementation | Evidence Class |
| :- | :--- | :--- | :-: |
| **S-01** | **Zero Experience Invention** | The LLM extraction schema strictly rejects extrapolating unverified candidate skills; absent skills are labeled "Unverified" or "Missing". | `[PRODUCT INFERENCE]` |
| **S-02** | **Calibrated Ambiguity Alerts** | If a job description is missing key technical criteria, the system renders a prominent amber alert badge: *"⚠️ Ambiguous Posting (Low Confidence: 45%)"*. | `[PRODUCT INFERENCE]` |
| **S-03** | **Visual Source Demarcation** | The UI uses distinct visual styling (containers, icons, fonts) to differentiate *Direct Employer Text* from *AI Interpretation & Recommendations*. | `[PRODUCT INFERENCE]` |
| **S-04** | **Ethical Framing & No Outcome Promises** | The UI never promises "Guaranteed Interview Offer"; language is framed as *"Qualification Alignment & Readiness"*. | `[FACT]` |
| **S-05** | **Inspectable Raw Data** | A persistent tab allows candidates to toggle and view the original raw JD text alongside structured entities. | `[PRODUCT INFERENCE]` |
| **S-06** | **User Reversibility & Overrides** | Candidates can edit any auto-extracted profile skill or manually override AI priority tier assignments with 1 click. | `[PRODUCT INFERENCE]` |
| **S-07** | **Zero Data Commercialization** | Candidate profile data and resume text are processed privately and never sold or shared with external recruiters. | `[FACT]` |
