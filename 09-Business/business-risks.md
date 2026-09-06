# Business Risk Management & Mitigation

## Executive Summary

This document evaluates the primary **commercial, financial, and market risks** facing AI Career Copilot.

Each risk is analyzed with early detection signals, proactive mitigation strategies, reactive contingency plans, and linked validation experiments to ensure the business model remains resilient.

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   BUSINESS RISK SEVERITY MATRIX                                  │
│                                                                                                  │
│   HIGH                                                                                           │
│    ▲                                                                                             │
│    │     ┌────────────────────────┐                    ┌────────────────────────┐                │
│    │     │ BR-04: Lifecycle Churn │                    │ BR-01: Budget Elasticity│               │
│ I  │     │ BR-05: Univ Sales Delay│                    │ BR-06: Callback Efficacy│               │
│ M  │     └────────────────────────┘                    └────────────────────────┘                │
│ P  │                                                                                             │
│ A  │     ┌────────────────────────┐                    ┌────────────────────────┐                │
│ C  │     │ BR-07: LLM Token COGS  │                    │ BR-02: Free Chatbot Com│               │
│ T  │     │ BR-08: Scope Sprawl    │                    │ BR-03: Paid Ad High CAC│               │
│    │     └────────────────────────┘                    └────────────────────────┘                │
│    └─────────────────────────────────────────────────────────────────────────────────────────▶   │
│   LOW                                   PROBABILITY                                         HIGH │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Comprehensive Business Risk Registry

| Risk ID | Identified Business Risk | Prob. | Impact | Early Warning Signal | Mitigation Strategy | Contingency Plan | Validation Experiment |
| :--- | :--- | :---: | :---: | :--- | :--- | :--- | :--- |
| **BR-01** | **Candidate Unwillingness to Pay:** Students resist paying $\$15/\text{mo}$ due to budget constraints. | **High** | **High** | Free-to-Paid conversion $<1.5\%$ on upgrade prompts. | Offer low-cost 4-month "Search Season Pass" ($\$39$ flat); emphasize ROI. | Pivot to University B2B subsidized institutional model. | EXP-BIZ-01 (Pricing Elasticity) |
| **BR-02** | **Commodity AI Perception:** Candidates feel raw ChatGPT prompts are "good enough." | **High** | **Med** | High drop-off after 1st evaluation; users copy JD to clipboard. | Emphasize quote citations, persistent snapshots, and 4-category taxonomy. | Deepen deterministic ATS gap structuring and export tools. | EXP-05 (Workflow Benchmark) |
| **BR-03** | **Unsustainable Paid CAC:** Digital ad acquisition costs exceed $\$25/\text{user}$. | **High** | **Med** | Blended CAC rising $> \$10$; paid ROI turning negative. | Mandate 100% organic campus club, Discord, and LinkedIn distribution. | Ban paid search/social ads; reallocate budget to campus club reps. | GTM-EXP-01 (Campus Activation) |
| **BR-04** | **Inherent Search Lifecycle Churn:** Candidates naturally churn in 2–4 months once hired. | **High** | **High** | Monthly churn $>40\%$ among successful candidates. | Design for high search intensity; monetize within the active 3-month window. | Introduce alumni transition & 1st-year career progression module. | Unit Economics Sensitivity Model |
| **BR-05** | **Lengthy University Procurement:** University career center sales cycle takes 12+ months. | **High** | **Med** | Enterprise leads stalled in procurement/FERPA security review. | Keep Freemium B2C as primary cash generator; treat university B2B as upside. | Offer free departmental pilot trials requiring zero IT integration. | GTM-EXP-03 (Univ Pilot Interest) |
| **BR-06** | **Lack of Interview Efficacy:** Candidates make high-confidence decisions but get zero interviews. | **Med** | **High** | Users report low callback rates despite "Strong Fit" applications. | Integrate Resume Framing Guidance (`CAP-17`) and gap upskill roadmaps. | Partner with specialized interview preparation and mock interview platforms. | Stage 4 Pilot Feedback |
| **BR-07** | **LLM Inference Cost Inflation:** Token API expenses compress gross margin below $70\%$. | **Med** | **Med** | Variable COGS per active user exceeding $\$3.00/\text{month}$. | Implement aggressive prompt caching, semantic embeddings, and local SLMs. | Restrict free tier weekly evaluation limit from 5 to 3 JDs. | Telemetry Cost Tracking |
| **BR-08** | **Premature Horizontal Expansion:** Expanding to non-technical roles dilutes product precision. | **Med** | **Med** | High manual overrides ($>30\%$) on non-technical job descriptions. | Strictly restrict marketing and onboarding to technical/analytical ICPs. | Re-enforce domain focus on Data, Business Analytics, and SWE roles. | Taxonomy Accuracy Audit |

*Note: Probabilities and impacts represent analytical risk modeling `[PRODUCT INFERENCE]`.*
