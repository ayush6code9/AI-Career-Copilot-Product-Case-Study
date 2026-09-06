# Job-Fit Analysis Experience (Explainability UX Specification)

This document defines the interface, information architecture, and cognitive interaction model for the **Job-Fit Analysis Screen**—the core explainability engine of **AI Career Copilot**.

---

## 1. Core UX Purpose

> **The primary question this screen answers is:**  
> **"Should I invest my limited time and effort applying to this job, and exactly why?"**

The interface intentionally rejects single opaque percentage badges (e.g., *"82% Match"*) in favor of a structured, multi-dimensional decision breakdown.

```
┌────────────────────────────────────────────────────────────────────────┐
│                     JOB-FIT ANALYSIS UI LAYOUT                         │
├────────────────────────────────────────────────────────────────────────┤
│ [1. OVERALL QUALITATIVE ASSESSMENT BADGE]                              │
│ "Strong Fit — Target Opportunity" | Confidence: High (90% JD clarity)  │
├────────────────────────────────────────────────────────────────────────┤
│ [2. STRATEGIC RECOMMENDATION & ACTION GUIDANCE]                        │
│ • Why apply: 3 core technical competencies directly verified.          │
│ • What to highlight: Frame your SQL E-commerce Capstone in intro.      │
│ • What to verify: Docker listed as preferred; confirm basic CLI usage. │
├────────────────────────────────────────────────────────────────────────┤
│ [3. MULTI-DIMENSIONAL REQUIREMENT BREAKDOWN & EVIDENCE CITATIONS]      │
│ ┌───────────────────────────┬────────────────────────────────────────┐ │
│ │ 🟢 Demonstrated Matches    │ "Python, SQL, Regression Modeling"     │ │
│ │                           │ ↳ Evidence: Capstone Repo + Coursework │ │
│ ├───────────────────────────┼────────────────────────────────────────┤ │
│ │ 🟡 Transferable Overlaps  │ "PyTorch ➔ Maps to TensorFlow Pref"    │ │
│ │                           │ ↳ Evidence: Deep Learning Class Project│ │
│ ├───────────────────────────┼────────────────────────────────────────┤ │
│ │ 🔴 Addressable Gaps       │ "Airflow (Learnable Preference)"       │ │
│ │                           │ ↳ Severity: Non-blocking; Learn on Job │ │
│ └───────────────────────────┴────────────────────────────────────────┘ │
├────────────────────────────────────────────────────────────────────────┤
│ [4. PRIMARY ACTIONS]                                                   │
│ [ ★ Add to Priority Queue ]   [ 💾 Save to Pipeline ]   [ ✕ Discard ]   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Information Architecture & Component Specification

### Section 1: Overall Assessment (Qualitative Fit Tiers)
Instead of a misleading single score, the system assigns one of 5 calibrated qualitative tiers:

| Qualitative Tier | Definition & User Meaning | Trigger Criteria |
| :--- | :--- | :--- |
| **Strong Fit (Target)** | High alignment across all hard requirements and core technical competencies `[PRODUCT INFERENCE]`. | Candidate profile satisfies 100% of hard requirements and ≥80% of core technical competencies with verified project evidence. |
| **Reasonable Fit (Viable)** | Solid alignment on core skills with 1–2 learnable secondary gaps `[PRODUCT INFERENCE]`. | Candidate meets hard requirements; has transferable equivalents for secondary tools. |
| **Stretch Opportunity (Reach)** | Strong foundational background but missing 1 key technical framework or commercial prerequisite `[PRODUCT INFERENCE]`. | Foundational skills present, but candidate lacks 1 substantial requirement (e.g., 1+ year specific domain tool). |
| **Low Fit (Misaligned)** | Substantial mismatch in core discipline, experience level, or non-negotiable prerequisites `[PRODUCT INFERENCE]`. | Missing mandatory degree/legal prerequisites or core technical stack completely unrelated. |
| **Insufficient Information** | Job description is too brief, vague, or filled with marketing fluff to make a confident evaluation `[PRODUCT INFERENCE]`. | JD contains <3 concrete technical requirements or omits role responsibilities. |

---

### Section 2: Requirement Breakdown & Evidence Citations

Every requirement extracted from the JD is classified into one of 6 taxonomy buckets and visually mapped to candidate profile evidence:

```
┌────────────────────────────────────────────────────────────────────────┐
│ TAXONOMY CLASSIFICATION TIERS                                          │
├────────────────────────────────────────────────────────────────────────┤
│ 1. HARD REQUIREMENT   │ Mandatory non-negotiable (e.g., BS in STEM).   │
│ 2. STRONG MATCH       │ Direct match with verified candidate evidence. │
│ 3. TRANSFERABLE MATCH │ Conceptual or adjacent tool equivalence.       │
│ 4. PREFERRED SKILL    │ Bonus tool; non-disqualifying.                 │
│ 5. MISSING SKILL      │ Unmet requirement; evaluated by severity.      │
│ 6. UNCLEAR REQUIREMENT│ Vague JD text flagged for candidate review.    │
└────────────────────────────────────────────────────────────────────────┘
```

#### Evidence Presentation Rules:
* Every **Strong Match** displays an expandable evidence tag citing the exact project or coursework source (e.g., *"Matched via: Customer Churn Capstone Project"*).
* Every **Transferable Match** explains the semantic equivalence (e.g., *"Tableau experience maps directly to listed PowerBI preference"*).
* **Zero Fabrication Guardrail**: If candidate profile does not contain evidence, the system marks the skill as *Unverified* or *Missing*, never hallucinating background `[PRODUCT INFERENCE]`.

---

### Section 3: Granular Gap Categorization

Gaps are explicitly segmented to prevent candidate self-disqualification and imposter syndrome:

| Gap Severity Tier | Meaning | Actionable User Guidance |
| :--- | :--- | :--- |
| **1. Blocking Gap** | Missing mandatory legal authorization, required degree level, or core foundational discipline `[FACT]`. | **Do Not Apply / Low Yield**: Saves user hours from guaranteed automated ATS rejection. |
| **2. Important Gap** | Primary daily tool missing with no direct equivalent in profile `[PRODUCT INFERENCE]`. | **Apply with Narrative Strategy**: Highlight fast learning curve or related conceptual projects. |
| **3. Learnable Gap** | Secondary syntax/tool that can be learned in <10 hours of self-study `[PRODUCT INFERENCE]`. | **Apply Immediately**: Treat as non-blocker; review syntax before interview screening. |
| **4. Nice-to-Have Gap** | Explicitly listed as "bonus / preferred" in job description `[FACT]`. | **Ignore as Blocker**: Reassures candidate that omission will not cause disqualification. |

---

### Section 4: Actionable Recommendations (Decision Next Steps)

The bottom panel delivers 3 concise, actionable directives:
1. **Strategic Why**: 1-sentence synthesis of why this role aligns with the candidate's target career trajectory.
2. **Interview Framing Cues**: Identifies which 1–2 portfolio projects the candidate should emphasize in their application narrative.
3. **Pre-Submission Checklist**: Specific ambiguities to verify on the employer portal before submitting.

---

### Section 5: Calibrated Uncertainty & AI Transparency

* **JD Quality Score**: Displays a clear badge indicating parsing confidence:
  * 🟢 **High Confidence (85–100%)**: Comprehensive JD with concrete responsibilities and explicit tooling.
  * 🟡 **Moderate Confidence (60–84%)**: Standard JD with moderate boilerplate.
  * 🔴 **Low Confidence (<60%)**: Vague JD. System renders alert: *"⚠️ This job posting uses broad, non-specific language. We recommend reading the raw description directly before making a final decision."*
* **Inspectable Prompts & Raw Data**: A toggle allows advanced candidates to inspect the raw extracted JD text alongside the structured breakdown to maintain total trust and auditability `[PRODUCT INFERENCE]`.
