# Business Decision Log

## Overview

This **Business Decision Log** documents the strategic commercial choices, monetization trade-offs, and go-to-market decisions governing AI Career Copilot.

Each record outlines the business context, alternative options evaluated, explicit sacrifices made, and pre-registered revisit triggers, providing interview-defensible proof of disciplined product and business judgment.

---

## Decision Records Summary

| ID | Strategic Commercial Decision | Core Trade-Off / Focus | Primary Rationale |
| :--- | :--- | :--- | :--- |
| **BD-01** | Technical & Analytical Beachhead | Niche Depth vs. Horizontal Breadth | Deep tool requirements enable structured quote citations and high organic campus virality. |
| **BD-02** | Direct-to-Consumer (B2C) First | Rapid Feedback vs. Institutional Scale | B2C validates willingness to pay in weeks; enterprise university sales take 12+ months. |
| **BD-03** | Monetization Post-Value Validation | Value Proof vs. Premature Revenue | Charging before proving decision confidence degrades user trust and kills early word-of-mouth. |
| **BD-04** | Value in Depth, Not Honest Fit Gating | Honest Decision Free Tier vs. Hard Paywall | Honest fit analysis is core value; paywalling truth creates distrust and high churn. |
| **BD-05** | University Sales as Phase 2 Channel | Bottom-Up Demand vs. Top-Down Dependency | Student proof points make university career center pitches significantly more compelling. |
| **BD-06** | Employer Monetization Excluded | Candidate-First Integrity vs. Recruiter Budget | Employer placement fees create severe conflicts of interest that corrupt objective fit analysis. |
| **BD-07** | Application Volume Banned as KPI | Decision Quality vs. Vanity Submission Counts | Monetizing on application volume incentivizes spamming, destroying candidate outcomes. |

---

## Detailed Business Decision Records

### BD-01: Early-Career Technical Candidates Selected as Primary Commercial Beachhead

* **Context:** The product could have targeted all job seekers horizontally or focused deeply on specific career verticals (e.g., tech vs. healthcare vs. finance).
* **Decision:** Restrict the initial commercial beachhead strictly to final-year students and recent graduates in technical/analytical disciplines (Data, Business Analytics, Product Analytics, Software/ML).
* **Alternatives Considered:**
  1. *Horizontal job seeker launch (Marketing, Sales, Operations, Tech).*
  2. *Executive / mid-career professional positioning.*
* **Rationale:** Technical roles feature dense tool and programming requirements that produce the highest evaluation friction and benefit most from 4-category taxonomy structuring. Furthermore, STEM cohorts possess highly concentrated, viral campus communication channels (Discord, club Slack channels) that keep acquisition costs near zero.
* **What Was Sacrificed:** Total addressable market (TAM) volume in year 1 in exchange for high product-market fit density and low CAC.
* **Metric & Experiment Affected:** Blended CAC, Free-to-Paid Conversion, GTM-EXP-01.
* **Revisit Trigger:** When weekly active users in the technical beachhead exceed $10,000$ and organic pull from non-technical majors exceeds $25\%$.

---

### BD-02: Direct-to-Consumer (B2C) Freemium Chosen as Initial Business Hypothesis

* **Context:** Educational and career technologies can be monetized via direct student subscriptions (B2C) or institutional university contracts (B2B).
* **Decision:** Design the initial go-to-market and monetization engine around a direct-to-consumer Freemium B2C model (`Option A`), treating University B2B as a Phase 2 expansion.
* **Alternatives Considered:**
  1. *Launch exclusively as a B2B SaaS platform selling to University Career Centers.*
  2. *Upfront paywall with 7-day free trial.*
* **Rationale:** University procurement cycles take 9–15 months and require extensive committee approvals, security reviews, and FERPA audits. Launching direct B2C provides immediate feedback on user engagement, core decision value, and pricing elasticity within days.
* **What Was Sacrificed:** Short-term annual recurring revenue (ARR) predictability and multi-year contract stability.
* **Metric & Experiment Affected:** Free-to-Paid Conversion, Monthly ARPU, EXP-BIZ-01.
* **Revisit Trigger:** If B2C student willingness to pay is $<1.5\%$ and student CAC exceeds $\$15$, pivot immediate focus to university institutional sponsorship.

---

### BD-03: Monetization Sequence Follows Product-Value Validation

* **Context:** Startups often debate whether to charge users on day one or build free engagement before introducing payment tiers.
* **Decision:** Introduce monetization only in **Release 2 / Stage 4 Pilot** after the core decision loop (W-HCCD) has been empirically validated.
* **Alternatives Considered:**
  1. *Charge $\$15/\text{month}$ from Day 1 of Release 1 Alpha.*
  2. *Keep the entire platform 100% free indefinitely and rely on future fundraising.*
* **Rationale:** Introducing paywalls before proving that the product actually reduces evaluation time and increases decision confidence will cause premature drop-off and pollute telemetry data. We must validate that candidates love the product before testing how much they will pay.
* **What Was Sacrificed:** Early nominal revenue generation during initial user testing.
* **Metric & Experiment Affected:** North Star Metric (W-HCCD), EXP-05 Benchmark, EXP-BIZ-01.
* **Revisit Trigger:** Once active weekly users reach $\ge 500$ and 7-day retention exceeds $35\%$, activate the monetization tier.

---

### BD-04: Honest Decision Value Kept Free; Premium Monetizes Depth & Workflow

* **Context:** Designing the free vs. paid tier boundary requires deciding whether to limit analysis quality (e.g., blur out gaps on free tier) or limit workflow volume.
* **Decision:** Keep the 5 qualitative fit tiers, 4-category taxonomy, gap severity classifications, and verifiable quote citations **100% free**. Monetize storage capacity ($>15$ snapshots), deep GitHub/SQL artifact parsing, and STAR-method interview preparation.
* **Alternatives Considered:**
  1. *Show fit score for free, but paywall the detailed skill gaps.*
  2. *Only show "Strong Fit" roles for free; paywall "Stretch" analysis.*
* **Rationale:** Blurring out gap analysis or holding back honesty destroys the core value proposition of transparent decision support. Candidates who feel tricked will immediately abandon the product. Giving full honesty on 5 JDs/week builds intense trust, driving upgrades when search intensity scales.
* **What Was Sacrificed:** Artificial conversion spikes caused by withholding basic answers.
* **Metric & Experiment Affected:** Paywall Abandonment Rate, Candidate Trust Score, EXP-BIZ-02.
* **Revisit Trigger:** If free tier usage is so satisfying that power users never upgrade despite evaluating $>20$ JDs, adjust the free snapshot storage ceiling from 15 to 10.

---

### BD-05: University Career Centers Positioned as Phase 2/3 GTM Channel

* **Context:** University career centers are natural institutional buyers, but engaging them too early can stall product development.
* **Decision:** Position university career centers as a **Phase 2/3 expansion channel** rather than an initial distribution dependency.
* **Alternatives Considered:**
  1. *Require university endorsement before launching on any campus.*
* **Rationale:** Career center deans are conservative and demand proven student placement outcomes before purchasing new software. By generating bottom-up student love and usage data on campus first, our eventual institutional sales pitch becomes overwhelmingly evidence-backed.
* **What Was Sacrificed:** Immediate top-down distribution to entire graduating classes on day one.
* **Metric & Experiment Affected:** Institutional Pilot Interest Rate, GTM-EXP-03.
* **Revisit Trigger:** When $>500$ students from a single university are actively using the free tier, initiate enterprise sales outreach to that university's Career Services Director.

---

### BD-06: Employer-Side Monetization Permanently Excluded as an Anti-Goal

* **Context:** Monetizing on employer recruiting budgets (job postings, candidate search, recruiter placement fees) offers massive revenue potential compared to student subscriptions.
* **Decision:** **Permanently reject employer-side monetization** and recruiter placement fees.
* **Alternatives Considered:**
  1. *Charge employers $\$2,000$ per hired candidate sourced through the platform.*
  2. *Allow employers to pay to boost their jobs in candidate queues.*
* **Rationale:** The moment an employer pays you for candidate placements, your algorithm is financially incentivized to push candidates toward paying employers, regardless of whether it is a good fit for the candidate. This fundamentally corrupts our core promise of objective, uncompromised decision support.
* **What Was Sacrificed:** Access to high-margin corporate recruiting budgets.
* **Metric & Experiment Affected:** Candidate Trust Score, Recommendation Accuracy.
* **Revisit Trigger:** Non-negotiable; permanent product integrity constraint.

---

### BD-07: Application Submission Volume Strictly Banned as a Commercial Metric

* **Context:** Many career platforms monetize or measure success based on total applications submitted (e.g., "We helped candidates apply to 100,000 jobs!").
* **Decision:** Strictly ban raw application volume or auto-apply counts from serving as a primary commercial metric, pricing tier gate, or investor KPI.
* **Alternatives Considered:**
  1. *Charge candidates $\$0.50$ per application submitted.*
  2. *Market the platform based on daily application volume submitted.*
* **Rationale:** Optimizing for application volume creates low-intent spam bots that damage candidate reputations and flood recruiter inboxes with garbage. Our economic value is **decision quality and triage precision**—saving candidates from wasting 50 hours on bad-fit roles.
* **What Was Sacrificed:** Easy vanity marketing metrics that look impressive in superficial pitch decks.
* **Metric & Experiment Affected:** North Star Metric (W-HCCD), Time-to-Prioritization.
* **Revisit Trigger:** Non-negotiable; core philosophical boundary.
