# Unit Economics & Financial Assumptions

## Executive Summary

This document outlines a **hypothetical unit economics and financial sensitivity model** for AI Career Copilot under the Freemium B2C subscription structure.

In strict compliance with the anti-fabrication guidelines, **no numbers in this document represent actual historical revenue, achieved conversions, or realized costs**. All figures represent **analytical planning models and sensitivity benchmarks** `[PLANNING ASSUMPTION]` designed to test the commercial viability boundaries of the product.

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                 UNIT ECONOMICS ARCHITECTURE                                      │
│                                                                                                  │
│   ACQUISITION (Blended CAC) ──▶ USER ACTIVITY (Free & Paid) ──▶ INFERENCE COGS (LLM Costs)       │
│                                           │                                   │                  │
│                                           ▼                                   ▼                  │
│                             SUBSCRIPTION ARPU ($15/mo) ──────▶ GROSS MARGIN (75-85%)             │
│                                           │                                   │                  │
│                                           └─────────────────┬─────────────────┘                  │
│                                                             ▼                                    │
│                                         LIFETIME VALUE (LTV) & PAYBACK PERIOD                    │
│                                         Target: LTV:CAC ≥ 3.0x | Payback < 2 Months              │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Core Mathematical Definitions & Formulas

The unit economics model is governed by the following standard SaaS financial formulas:

$$\text{Gross Profit per Paid User} = ARPU \times \text{Gross Margin \%}$$

$$\text{Average Customer Lifetime (Months)} = \frac{1}{\text{Monthly Churn Rate}}$$

$$\text{Customer Lifetime Value (LTV)} = \frac{ARPU \times \text{Gross Margin \%}}{\text{Monthly Churn Rate}}$$

$$\text{LTV : CAC Ratio} = \frac{LTV}{CAC_{\text{Paid}}}$$

$$\text{CAC Payback Period (Months)} = \frac{CAC_{\text{Paid}}}{ARPU \times \text{Gross Margin \%}}$$

---

## 2. Cost of Goods Sold (COGS) & AI Inference Breakdown

A critical variable in AI software unit economics is the variable cost of Large Language Model (LLM) API inference per evaluation:

| Operational Parameter | Baseline Assumption `[PLANNING ASSUMPTION]` | Unit Calculation | Monthly Cost per Active User |
| :--- | :--- | :--- | :--- |
| **Profile Parsing & Verification** | 1 Resume per candidate (Once upon onboarding) | $\sim 2,000$ tokens $\times \$0.000005$/token | $\sim \$0.01$ (One-off amortized) |
| **JD Ingestion & 4-Category Taxonomy** | 15 JDs evaluated / month | $\sim 1,500$ tokens $\times 15 \times \$0.000003$/token | $\sim \$0.07$ / month |
| **Deep Fit Evaluation & Quote Citations** | 15 JDs evaluated / month | $\sim 3,000$ tokens $\times 15 \times \$0.000005$/token | $\sim \$0.23$ / month |
| **Database Storage & Cloud Hosting** | 15 Immutable Snapshots + App State | PostgreSQL + S3 Storage allocation | $\sim \$0.15$ / month |
| **Total Variable Cost per Active Free User** | — | — | **$\sim \$0.46$ / user / month** |
| **Total Variable Cost per Active Paid User** | 40 JDs evaluated + STAR Prep Drawer | Higher token volume + Code artifact parsing | **$\sim \$1.85$ / user / month** |

*Economic Takeaway:* At $\$15/\text{month}$ subscription pricing, direct AI inference and hosting COGS ($\sim \$1.85/\text{month}$) yield a **Gross Margin of approximately $87.6\%$**, well within healthy SaaS software benchmarks.

---

## 3. Financial Sensitivity Analysis (3 Scenarios)

Because early-career job search has an inherent lifecycle (candidates unsubscribe once hired, creating high natural churn), the model evaluates three scenarios:

| Metric / Parameter | Conservative Scenario | Base Case Scenario | Optimistic Scenario |
| :--- | :---: | :---: | :---: |
| **Monthly Subscription Price (ARPU)** | $\$12.00$ `[PLANNING ASSUMPTION]` | $\$15.00$ `[PLANNING ASSUMPTION]` | $\$19.00$ `[PLANNING ASSUMPTION]` |
| **Gross Margin \% (after AI COGS)** | $75.0\%$ | $82.0\%$ | $88.0\%$ |
| **Monthly Gross Profit per Paid User** | $\$9.00$ | $\$12.30$ | $\$16.72$ |
| **Monthly Churn Rate during Search** | **$35.0\%$** ($\sim 2.8$ mo lifetime) | **$25.0\%$** ($\sim 4.0$ mo lifetime) | **$18.0\%$** ($\sim 5.5$ mo lifetime) |
| **Customer Lifetime Value (LTV)** | **$\$25.71$** | **$\$49.20$** | **$\$92.89$** |
| **Blended Customer Acquisition Cost (CAC)**| $\$12.00$ (Mixed Ads/Campus) | **$\$8.00$** (Organic Community Led)| **$\$4.00$** (Viral Peer Loops) |
| **LTV : CAC Ratio** | **$2.14\times$** (Viable but tight) | **$6.15\times$** (Highly attractive) | **$23.22\times$** (Exceptional) |
| **CAC Payback Period** | **$1.33 \text{ Months}$** | **$0.65 \text{ Months}$** | **$0.24 \text{ Months}$** |
| **Free-to-Paid Conversion Rate** | $2.5\%$ | $4.5\%$ | $7.0\%$ |

---

## 4. Key Financial Drivers & Vulnerabilities

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   FINANCIAL SENSITIVITY DRIVERS                                  │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 1. SEARCH LIFECYCLE CHURN VS. CAC                                                                │
│    Unlike B2B SaaS with multi-year retention, job seekers naturally churn after getting hired.   │
│    Therefore, maintaining a BLENDED CAC < $10 is an existential prerequisite for B2C viability. │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 2. FREE-TO-PAID CONVERSION VELOCITY                                                              │
│    Because free users incur ~$0.46/month in AI inference costs, conversion must remain ≥ 3.5%    │
│    to ensure paying subscribers comfortably subsidize active free exploration.                   │
├──────────────────────────────────────────────────────────────────────────────────────────────────┤
│ 3. TOKEN INFERENCE INFLATION                                                                     │
│    If LLM context windows or reasoning architectures increase token consumption by 5x, gross    │
│    margins compress from 85% to <60%, requiring smaller, fine-tuned extraction models.          │
└────────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. What Must Be Empirically Validated Before Trusting This Model?

To graduate this financial model from analytical planning assumptions to an investment-grade business plan, the team must validate:

1. **True Natural Churn Rate:** Does the average active candidate use the product for 2 months, 4 months, or 6 months during an academic search cycle?
2. **True Free-to-Paid Conversion:** Will at least $3.5\text{--}5.0\%$ of active users pay $\$15/\text{month}$ when reaching capacity or interview stages?
3. **Blended Organic CAC:** Can campus club partnerships and LinkedIn content sustainably deliver new users at $<\$8$ per activated candidate?
4. **Token Cost Stability:** Can prompt caching, batch embeddings, and lightweight SLMs (Small Language Models) keep AI COGS below $\$2.00$ per heavy active user?
