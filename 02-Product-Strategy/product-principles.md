# Product Principles

These six product principles serve as the decision-making filter for product prioritization, feature scoping, UX design, and architectural trade-offs in **AI Career Copilot**.

---

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CORE PRODUCT PRINCIPLES                         │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Explainability Over Black-Box Scores                                │
│ 2. Decision Quality Over Application Volume                            │
│ 3. User Agency & Control Over Blind Automation                         │
│ 4. Calibrated Uncertainty Over False Precision                         │
│ 5. Actionable Next Steps Over Data Dumps                               │
│ 6. Minimal Input Friction Over Exhaustive Profiling                    │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Explainability Over Black-Box Scores

* **Meaning**: Never present a single opaque percentage or badge (e.g., "87% Match" or "Top Applicant") without an immediate, inspectable rationale detailing *why* the candidate aligns or where gaps exist.
* **Why It Matters**: Black-box scores create false confidence or induce imposter syndrome without empowering candidates to make informed decisions. Trust is built through transparent reasoning `[PRODUCT INFERENCE]`.
* **Product Implication**: Every fit evaluation must render 3 distinct qualitative buckets: **Demonstrated Core Matches**, **Transferable Project Overlaps**, and **Addressable Skill Gaps**.

---

## 2. Decision Quality Over Application Volume

* **Meaning**: Measure product success by how effectively candidates identify and focus on high-yield, role-aligned opportunities, not by the sheer quantity of resumes blasted.
* **Why It Matters**: The labor market penalizes generic spam applications with near-zero response rates. High-conviction, tailored applications convert at significantly higher rates `[DESK RESEARCH]`.
* **Product Implication**: The UI will emphasize a prioritized queue of top 5–10 high-conviction roles rather than an endless scrolling feed of 500 unranked jobs.

---

## 3. User Agency & Control Over Blind Automation

* **Meaning**: The AI acts as an analytical co-pilot and advisor, keeping the candidate in the driver's seat for final judgment, tailoring, and official application submission.
* **Why It Matters**: Automated background submission bots disconnect candidates from their own job search, leading to poor interview performance when candidates are caught unprepared by recruiter reach-outs `[ASSUMPTION]`.
* **Product Implication**: We deliberately do not build one-click auto-submit bots; instead, we provide 1-click JD evaluation, priority sorting, and structured prep context for direct candidate submission.

---

## 4. Calibrated Uncertainty Over False Precision

* **Meaning**: Clearly communicate the confidence and ambiguity level of AI inferences rather than pretending LLM interpretations are absolute hiring truths.
* **Why It Matters**: Job descriptions are notoriously ambiguous and recruiters have subjective hiring preferences. Presenting AI fit scores as indisputable facts misleads candidates `[PRODUCT INFERENCE]`.
* **Product Implication**: Use qualitative certainty tiers (e.g., *"Explicit Requirement"* vs. *"Likely Preferred"* vs. *"Ambiguous / Unstated"*) and explicitly flag when a JD is too vague for high-confidence matching.

---

## 5. Actionable Guidance Over Information Overload

* **Meaning**: Every piece of analytical information presented to the candidate must lead directly to a clear next action.
* **Why It Matters**: Early-career candidates are already drowning in job-search advice and fragmented information. Adding more complex dashboards without actionable guidance worsens cognitive fatigue `[ASSUMPTION]`.
* **Product Implication**: When a gap is identified (e.g., missing Docker knowledge), the system explicitly indicates whether the candidate should **Apply Anyway (Transferable)**, **Highlight Alternative Experience**, or **Upskill Before Applying**.

---

## 6. Minimal Input Friction Over Exhaustive Profiling

* **Meaning**: Maximize value delivery from the candidate's existing artifacts (resumes, GitHub links, project text) rather than demanding tedious multi-step manual onboarding questionnaires.
* **Why It Matters**: High onboarding friction causes massive initial user drop-off before the candidate ever experiences core product value `[FACT]`.
* **Product Implication**: Allow candidates to bootstrap their baseline profile instantly by uploading an existing resume and pasting a GitHub/portfolio link, parsing structured parameters automatically with user review.
