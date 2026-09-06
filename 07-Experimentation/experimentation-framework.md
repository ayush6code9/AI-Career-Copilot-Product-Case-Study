# Product Experimentation Framework & Validation Philosophy

This document establishes the scientific methodology, progressive uncertainty reduction model, and AI safety validation principles for **AI Career Copilot**.

---

## 1. The Purpose of Experimentation: De-Risking Core Product Decisions

```
┌────────────────────────────────────────────────────────────────────────┐
│                     THE VALIDATION PROGRESSION CHAIN                   │
├────────────────────────────────────────────────────────────────────────┤
│ Problem Discovery  ──▶  Falsifiable Hypothesis  ──▶  Targeted Test     │
│        │                                                    │          │
│        ▼                                                    ▼          │
│ Grounded Learning  ◀──  Pre-Commit Decision Rule  ◀──  Primary Metric  │
└────────────────────────────────────────────────────────────────────────┘
```

Experimentation in AI Career Copilot is not an exercise in testing cosmetic UI variants (e.g., button colors or font sizes). It is a disciplined mechanism to validate **critical product mechanics, decision velocity, AI explainability trust, and candidate time allocation** before committing engineering resources at scale `[PRODUCT INFERENCE]`.

---

## 2. Epistemological Standards: Distinguishing Information Classes

To maintain senior-level rigor and prevent self-delusion, the product team strictly distinguishes between three classes of information:

| Information Class | Definition | Operational Standard in Case Study |
| :--- | :--- | :--- |
| **Assumption** `[ASSUMPTION]` | An unverified premise about user behavior, market dynamics, or technical feasibility accepted without proof to scope the initial model. | Must be cataloged in the Hypothesis Backlog and systematically tested. |
| **Hypothesis** `[HYPOTHESIS]` | A precise, falsifiable prediction stating expected user outcomes under specific interventions ($If\ [Intervention] \rightarrow Then\ [Outcome]$). | Must have defined primary metrics, guardrail thresholds, and decision rules. |
| **Validated Evidence** `[FACT]` | Empirical ground truth confirmed through statistically valid experiments, benchmark data, or verified user observations. | Only claimed when actual production telemetry or verified research exists. |

---

## 3. Progressive Uncertainty Reduction Model

Early-stage products fail when they prematurely deploy complex A/B tests before validating foundational user comprehension. AI Career Copilot follows a 6-stage progressive uncertainty reduction sequence:

```
┌────────────────────────────────────────────────────────────────────────┐
│               PROGRESSIVE UNCERTAINTY REDUCTION SEQUENCE               │
├────────────────────────────────────────────────────────────────────────┤
│ 1. DISCOVERY RESEARCH    ➔ Verify the problem exists (Pain points).    │
│ 2. PROTOTYPE VALIDATION  ➔ Test comprehension of concepts (Fit tiers).│
│ 3. USABILITY TESTING     ➔ Test interaction mechanics (Tooltips/Drag). │
│ 4. COHORT PILOT          ➔ Test repeated workflow & retention (3-Week).│
│ 5. CONTROLLED A/B TEST   ➔ Test causal lift at statistical scale.     │
│ 6. SCALE & OPTIMIZATION  ➔ Continuous prompt & model optimization.     │
└────────────────────────────────────────────────────────────────────────┘
```

### Why Early-Stage Products Must Not Jump Straight to A/B Testing
1. **Sample Size & Statistical Power**: In early MVP stages, candidate traffic is insufficient to power multi-variant A/B tests with statistical significance without running tests for months `[FACT]`.
2. **Qualitative "Why" Over Quantitative "What"**: A/B tests indicate *which* variant won, but cannot explain *why* a candidate doubted an AI match. Rapid qualitative prototyping uncovers mental model breakdowns in hours `[PRODUCT INFERENCE]`.
3. **Foundational Risk First**: We must prove that candidates understand qualitative fit tiers (Usability) before measuring marginal conversion lifts (A/B testing).

---

## 4. AI-Specific Experimentation & Dual-Track Validation

Generative AI decision products require a **Dual-Track Validation Model** that evaluates technical model quality independently from user behavioral impact:

```
                                  DUAL-TRACK VALIDATION
                   ┌────────────────────────┼────────────────────────┐
                   ▼                                                 ▼
┌──────────────────────────────────────┐          ┌──────────────────────────────────────┐
│       TRACK 1: AI MODEL QUALITY      │          │       TRACK 2: USER EXPERIENCE       │
│                                      │          │                                      │
│ • Grounding Fidelity (No hallucinations)│       │ • Decision Conviction & Velocity     │
│ • Requirement Extraction Accuracy    │          │ • Evidence Tooltip Inspection Rate   │
│ • Gap Severity Classification F1     │          │ • Queue Execution & Application Rate │
│ • Ambiguity Detection Calibration    │          │ • Retention & Pipeline Progression   │
└──────────────────────────────────────┘          └──────────────────────────────────────┘
```

* **Core Rule**: High UX conversion cannot justify a model that hallucinates candidate evidence. If Track 1 fails, Track 2 cannot ship `[PRODUCT INFERENCE]`.

---

## 5. Experimentation Anti-Patterns: Mistakes We Avoid

```
┌────────────────────────────────────────────────────────────────────────┐
│                     EXPERIMENTATION ANTI-PATTERNS                      │
├────────────────────┬───────────────────────────────────────────────────┤
│ ANTI-PATTERN       │ WHY IT DESTROYS PRODUCT QUALITY                   │
├────────────────────┼───────────────────────────────────────────────────┤
│ 1. Testing Colors  │ Wastes cycles on cosmetic details instead of the  │
│    Over Decisions  │ core decision-support value loop.                 │
├────────────────────┼───────────────────────────────────────────────────┤
│ 2. Single-Metric   │ Celebrating a conversion lift while ignoring AI   │
│    Tunnel Vision   │ hallucinations or false confidence guardrails.    │
├────────────────────┼───────────────────────────────────────────────────┤
│ 3. Moving Target   │ Changing prompt templates, UI layout, and ranking │
│    Multi-Variables │ weights simultaneously without attribution.       │
├────────────────────┼───────────────────────────────────────────────────┤
│ 4. Fabricated Stat │ Declaring a hypothesis "proven" with 12 users     │
│    Significance    │ without statistical power calculations.           │
├────────────────────┼───────────────────────────────────────────────────┤
│ 5. Optimizing Spam │ Measuring success by total applications rather    │
│    Submission      │ than candidate conviction and interview readiness.│
└────────────────────┴───────────────────────────────────────────────────┘
```
