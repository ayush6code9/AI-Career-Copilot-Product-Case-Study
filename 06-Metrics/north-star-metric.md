# North Star Metric Specification

This document defines the single North Star Metric for **AI Career Copilot**, establishing its formal operational definition, strategic rationale, alternative evaluations, and structural limitations.

---

## 1. The North Star Metric

```
┌────────────────────────────────────────────────────────────────────────┐
│                        NORTH STAR METRIC (NSM)                         │
│                                                                        │
│             Weekly High-Confidence Career Decisions (W-HCCD)           │
│                                                                        │
│ "The number of unique job opportunities where a candidate has reviewed │
│ the explainable qualification breakdown and executed a deliberate,     │
│ committed triage action (Prioritized, Saved with Notes, or Discarded)."│
└────────────────────────────────────────────────────────────────────────┘
```

$$\text{W-HCCD} = \sum \text{Deliberate Triage Actions following Qualified Review per Active Candidate per Week}$$

---

## 2. Precise Operational Definitions

To eliminate ambiguity, the component terms of the North Star Metric are strictly defined:

### 2.1 "Meaningfully Evaluated"
An evaluation is classified as *Meaningful* if and only if:
1. The system successfully structures the job description into requirement entities.
2. The candidate views the Job-Fit Breakdown card for a dwell time of $\ge 15\text{ seconds}$ (ruling out immediate bounce or zero-second scrolling) `[DESIGN TARGET]`.
3. The candidate inspects at least one requirement bucket (Demonstrated Matches, Transferable Overlaps, or Gap Severity Tiers).

### 2.2 "High-Confidence Decision"
A decision is classified as a *High-Confidence Decision* when the candidate executes one of three explicit, intentional triage events after reviewing the explanation:
* **Path A (Committed Pursuit)**: Explicitly moving the role to **Tier 1 (High-Fit Target)** or **Tier 2 (Growth Stretch)** in the Opportunity Queue.
* **Path B (Deliberate Discard)**: Explicitly marking the role as **Discarded / Low Conviction** after viewing blocker gaps, thereby eliminating tab clutter and avoiding wasted application hours.
* **Path C (Contextual Save)**: Saving to Pipeline with customized candidate preparation notes.

*Note: Passive tab closures or abandonment without an explicit triage click are classified as Inconclusive Drop-offs and do NOT count toward W-HCCD.*

---

## 3. Why This Metric Represents True Customer Value

```
┌────────────────────────────────────────────────────────────────────────┐
│                      VALUE TRANSMISSION CHAIN                          │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Candidate imports an ambiguous, bloated job posting.                │
│ 2. System deconstructs requirements and surfaces grounded evidence.    │
│ 3. Candidate gains immediate clarity on true qualification alignment.  │
│ 4. Candidate makes an informed, intentional decision (Apply vs Skip).  │
│ 5. Wasted hours on mismatched roles drop; interview readiness rises.   │
└────────────────────────────────────────────────────────────────────────┘
```

* **Captures Both Positive and Negative Clarity**: In job search, deciding **NOT** to apply to a 10-hour application after identifying a fatal blocker gap is just as valuable as deciding to apply to a high-fit role. W-HCCD values both outcomes equally `[PRODUCT INFERENCE]`.
* **Measures Decision Quality over Vanity Activity**: It prevents rewarding mindless job scrolling and penalizes passive abandonment.
* **Connects Directly to Primary JTBD**: Directly reflects whether the user answered: *"Should I invest my limited time and effort in this job, and why?"* `[JTBD 1]`.

---

## 4. Evaluation and Rejection of Alternative Candidates

| Candidate Metric | Why Considered | Why Rejected as North Star |
| :--- | :--- | :--- |
| **Total Applications Submitted** | Direct output of job search. | **Misaligned Incentives**: Encourages auto-apply spam bots; ignores decision quality and conversion rate `[DESK RESEARCH]`. |
| **Total Jobs Analyzed** | Direct measure of AI model usage. | **Vanity Metric**: High volume of analyses without decisions indicates browsing paralysis and user confusion `[PRODUCT INFERENCE]`. |
| **Weekly Active Users (WAU)** | Standard SaaS metric. | **Too Broad**: Measures login frequency without indicating whether the candidate received any career decision value `[FACT]`. |
| **Average Fit Score of Applied Jobs** | Measures applicant qualification. | **Gaming Risk**: Distorts user behavior toward applying only to 100% safety roles, discouraging viable stretch opportunities `[PRODUCT INFERENCE]`. |
| **Job Offer Acceptance Rate** | Ultimate end-state career outcome. | **Extreme Lagging Indicator & Attribution Loss**: Offer cycles take 2–4 months; heavily influenced by offline interview performance beyond software control `[FACT]`. |

---

## 5. Input Metric Drivers of the North Star (Decomposition)

```
                            ┌─────────────────────────────────────────┐
                            │    W-HCCD (North Star Metric)           │
                            └────────────────────▲────────────────────┘
                                                 │
                   ┌─────────────────────────────┼─────────────────────────────┐
                   │                             │                             │
┌──────────────────────────────────┐ ┌──────────────────────────────────┐ ┌──────────────────────────────────┐
│        INPUT DRIVER 1:           │ │        INPUT DRIVER 2:           │ │        INPUT DRIVER 3:           │
│        Activation Flow           │ │     Explainability Depth         │ │      Triage Conversion           │
│                                  │ │                                  │ │                                  │
│ • Profile Readiness Rate         │ │ • Time-to-Evaluation (<90s)      │ │ • Meaningful Review-to-Decision  │
│ • Clean JD Ingestion Volume      │ │ • Grounded Evidence Inspect Rate │ │   Conversion Rate (>65% target)  │
└──────────────────────────────────┘ └──────────────────────────────────┘ └──────────────────────────────────┘
```

---

## 6. Structural Limitations of W-HCCD

1. **Self-Reported Intent**: Marking a job as "Prioritized" does not guarantee the candidate completed the external application on the company portal `[FACT]`. *(Mitigated by measuring downstream `Marked as Applied` and `Interview Context Retrieval` events).*
2. **Quality vs. Agreement**: If an AI model hallucinates a match and the user accepts it out of automation bias, W-HCCD would still register a decision `[PRODUCT INFERENCE]`. *(Mitigated by strict AI Guardrail GR-02: Unsupported Evidence Rate).*
