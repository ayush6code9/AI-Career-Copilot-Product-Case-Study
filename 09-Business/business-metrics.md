# Business Metrics & Commercial Telemetry

## Executive Summary

This document establishes the **Commercial Metric Hierarchy** for AI Career Copilot, defining how business performance, revenue drivers, and monetization telemetry connect to the product outcome metrics established in [06-Metrics/metrics-framework.md](file:///Users/ayushkumarsingh/Downloads/AI-Career-Copilot-Product-Case-Study/06-Metrics/metrics-framework.md).

A strict principle governing this case study is that **revenue is downstream of demonstrated user value**. The product's North Star Metric remains **Weekly High-Confidence Career Decisions (W-HCCD)**; commercial metrics measure the economic sustainability of delivering that core value.

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   METRIC HIERARCHY INTEGRATION                                   │
│                                                                                                  │
│   NORTH STAR METRIC: Weekly High-Confidence Career Decisions (W-HCCD)                            │
│        │                                                                                         │
│        ▼                                                                                         │
│   PRODUCT VALUE METRICS (Level 1)                                                                │
│   • Fit Analysis Completion Rate (≥80%) • Evidence Inspection Rate (≥60%) • Override (10-30%)   │
│        │                                                                                         │
│        ▼                                                                                         │
│   ACTIVATION & RETENTION METRICS (Level 2)                                                       │
│   • 7-Day Triage Return Rate (≥35%)     • Snapshot Reference Frequency    • Profile Completion   │
│        │                                                                                         │
│        ▼                                                                                         │
│   MONETIZATION & REVENUE METRICS (Level 3)                                                       │
│   • Free-to-Paid Conversion (≥4.0%)     • Monthly ARPU ($15)              • LLM COGS / Decision  │
│        │                                                                                         │
│        ▼                                                                                         │
│   ACQUISITION & UNIT ECONOMICS (Level 4)                                                         │
│   • Blended CAC (<$8.00)                • LTV : CAC Ratio (≥3.0x)         • CAC Payback (<2 Mos) │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Product Outcome vs. Business Commercial Metrics

| Category | Metric Name | Definition / Formula | Telemetry Source | Strategic Function |
| :--- | :--- | :--- | :--- | :--- |
| **Product (North Star)** | **Weekly High-Confidence Career Decisions (W-HCCD)** | Count of qualified triage actions ($\ge 15\text{s}$ review) with $\ge 4/5$ confidence rating. | In-App Telemetry & Exit Survey | Measures core problem resolution; prevents vanity focus. |
| **Product (Value)** | **Evidence Inspection Rate** | $\frac{\text{Sessions with Quote Citation Drawer Expanded}}{\text{Total Completed Fit Analyses}}$ | Client Click Event | Measures candidate engagement with AI transparency. |
| **Product (Agency)**| **Fit Manual Override Rate** | $\frac{\text{Fit Recommendations Overridden by Candidate}}{\text{Total Completed Fit Analyses}}$ | Recommendation Event | Guardrail against automation bias ($10\text{--}30\%$ healthy band). |
| **Product (Trust)** | **Unsupported Evidence Rate** | $\frac{\text{AI Citations Missing from Candidate Profile}}{\text{Total Evaluated Citations}}$ | Grounding Audit Pipeline | Absolute safety launch gate ($<1.0\%$). |
| **Business (Conversion)**| **Free-to-Paid Conversion Rate** | $\frac{\text{Free Users Subscribing to Copilot Pro}}{\text{Total Weekly Active Free Evaluators}}$ | Stripe / Payment Webhook | Measures monetization velocity and willingness to pay. |
| **Business (Revenue)** | **Average Revenue Per User (ARPU)** | $\frac{\text{Total Monthly Subscription Revenue}}{\text{Total Active Paid Subscribers}}$ | Billing System | Measures average monetization yield ($\sim \$15/\text{mo}$). |
| **Business (Cost)** | **Inference Cost per Decision** | $\frac{\text{Total Monthly LLM API Invoices}}{\text{Total High-Confidence Decisions Completed}}$ | API Gateway Logs | Gross margin protector; monitors token inflation. |
| **Business (Acquisition)**| **Blended Customer Acquisition Cost** | $\frac{\text{Total Sales, Marketing \& Workshop Spend}}{\text{Total New Activated Candidates}}$ | Marketing Ledger | Ensures acquisition stays within sustainable LTV bounds. |
| **Business (Efficiency)**| **LTV : CAC Ratio** | $\frac{\text{Gross Profit per User} \div \text{Monthly Churn}}{\text{Blended CAC}}$ | Financial Model | Measures long-term economic scalability ($>3.0\times$). |

---

## 2. Commercial Guardrails & Kill-Switches

To prevent short-term monetization tactics from degrading the candidate experience, the following **Commercial Guardrail Thresholds** are enforced:

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   COMMERCIAL GUARDRAIL THRESHOLDS                                │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 1. BLENDED CAC CEILING (< $10.00 `[PLANNING ASSUMPTION]`)                                        │
│    If blended CAC exceeds $10.00, immediately halt paid marketing channels and revert to 100%    │
│    campus community and organic referral distribution.                                           │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 2. GROSS MARGIN FLOOR (> 75.0% `[PLANNING ASSUMPTION]`)                                          │
│    If token inference costs compress gross margin below 75%, activate prompt compression and     │
│    transition secondary extraction tasks to lightweight fine-tuned SLMs.                         │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 3. ACTIVE SEARCH CHURN CEILING (< 35.0% `[PLANNING ASSUMPTION]`)                                 │
│    If candidates churn before completing 3 high-confidence evaluations (indicating premature     │
│    abandonment rather than placement), investigate onboarding and UI friction.                   │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 4. PAYWALL ABANDONMENT RATE (< 20.0% `[PLANNING ASSUMPTION]`)                                     │
│    If displaying upgrade banners causes >20% of free users to abandon the core evaluation loop, │
│    redesign the paywall trigger to appear only after decision completion.                        │
└────────────────────────────────────────────────────────────────────────────────────────────────┘
```
