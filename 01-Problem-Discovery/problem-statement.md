# Problem Statement & Problem Framing

## Initial Problem
"Final-year students and recent graduates struggle to decide which job opportunities are worth pursuing because job opportunities are fragmented, job requirements are difficult to evaluate against their own profile, and candidates have limited time to assess every opportunity."

---

## Problem Context
`[FACT]` Early-career job seekers enter an open labor market characterized by decentralized hiring across LinkedIn, Indeed, Handshake, company career portals, and niche job boards.  
`[DESK RESEARCH]` Entry-level technical and analytical job postings (e.g., Data Analyst, Software Engineer, Product Analyst) frequently include inflated qualification checklists (e.g., requesting 2–3 years of experience for "entry-level" titles or extensive laundry lists of tools and frameworks).  
`[PRODUCT INFERENCE]` College seniors and recent graduates have uncalibrated mental models of how their academic coursework, capstone projects, and self-directed learning map to employer requirements. Consequently, candidates face an evaluation barrier before they even begin drafting an application.

---

## Symptoms
Symptoms are observable indicators of distress or inefficiency, but not the foundational cause itself:

1. **Volume-Seeking Spray-and-Pray Behavior**: Candidates submit dozens or hundreds of generic applications with low conversion rates `[PRODUCT INFERENCE]`.
2. **Search Fatigue & Paralysis**: Spending hours scrolling job feeds without deciding which jobs to prioritize or apply to `[ASSUMPTION]`.
3. **Application Anxiety & Imposter Syndrome**: Hesitating to apply to roles where 1 or 2 listed requirements are missing, assuming absolute disqualification `[ASSUMPTION]`.
4. **Scattered Application Tracking**: Maintaining incomplete spreadsheets, browser bookmarks, or relying on inbox search to track status `[FACT]`.

---

## Root Causes
Root causes explain *why* the symptoms occur:

1. **Information Asymmetry & Ambiguity in Job Descriptions (JDs)**: JDs conflate "must-have" core competencies with "nice-to-have" preferences without clarifying candidate trade-offs `[DESK RESEARCH]`.
2. **Cognitive Translation Gap**: Candidates lack a reliable mechanism to translate their static profile (resume, projects, academic skills) into a structured comparison against ambiguous job criteria `[PRODUCT INFERENCE]`.
3. **Absence of Explainable Fit Criteria**: Existing platforms offer opaque matching signals (e.g., "Top Applicant" badges or black-box percentages) without explaining the underlying rationale or identifying specific addressable gaps `[FACT]`.
4. **Fragmented Workflows**: Discovery, evaluation, tailoring, and tracking occur across disconnected tools (job boards, document editors, spreadsheets), increasing cognitive switching costs `[FACT]`.

---

## User Consequences

| Dimension | Impact on User |
| :--- | :--- |
| **Time Allocation** | High effort spent on manual JD decoding and low-probability applications, leaving insufficient time for targeted preparation `[PRODUCT INFERENCE]`. |
| **Decision Quality** | Choices are driven by job board algorithmic rankings or sheer volume rather than strategic qualification alignment `[ASSUMPTION]`. |
| **Emotional Toll** | Elevated burnout, fatigue, and self-doubt resulting from low response rates and opaque rejection feedback `[ASSUMPTION]`. |

---

## Current Alternatives

1. **Horizontal Job Aggregators (LinkedIn, Indeed, Glassdoor)**: Excellent for indexing job postings; poor for personalized qualification decoding and explainable fit analysis `[FACT]`.
2. **University Career Portals (Handshake, Campus Placement Portals)**: Filtered for student hiring, but listings are often limited in volume, geographically constrained, or lack deep role-specific fit analysis `[FACT]`.
3. **Spreadsheets & Notion Templates**: Used for tracking applications manually; require tedious manual data entry and lack automated fit insights `[FACT]`.
4. **Generative AI Chatbots (ChatGPT, Claude)**: Used ad-hoc by candidates to paste JDs and ask for fit summaries; disjointed, unorganized, and lacks unified tracking or multi-job ranking `[FACT]`.
5. **Mass-Application / Auto-Apply Bots**: Mechanically blast resumes to hundreds of postings; increases candidate spam volume, damages candidate brand, and fails to solve the underlying decision and skill-alignment problem `[PRODUCT INFERENCE]`.

---

## Why Existing Solutions May Be Insufficient

| Alternative | What It Does Well | Where It Breaks Down for Early-Career Candidates |
| :--- | :--- | :--- |
| **Aggregators (LinkedIn/Indeed)** | Search volume, company data, alert notifications | Opaque fit indicators; does not evaluate candidate project depth against JD nuances `[FACT]`. |
| **Ad-Hoc LLM Prompts** | Text summarization, ad-hoc gap explanations | No persistent profile context, no automated comparison across multiple roles, high manual friction `[PRODUCT INFERENCE]`. |
| **Manual Spreadsheets** | Customizable pipeline organization | Completely disconnected from job data; zero intelligence or automated evaluation `[FACT]`. |
| **Auto-Apply Bots** | Maximizes raw submission counts | Degrades application quality, ignores role fit, increases noise for recruiters, provides zero candidate clarity `[PRODUCT INFERENCE]`. |

---

## Evidence vs Assumptions

```
┌────────────────────────────────────────────────────────────────────────┐
│ EVIDENCE & DESK RESEARCH (Ground Truth)                                │
│ • JDs have variable terminology and ambiguous requirement tiers.      │
│ • Candidates use multiple disparate tools to search and track.         │
│ • Existing job boards do not provide transparent fit reasoning.       │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ informs
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│ ASSUMPTIONS & INFERENCES (Requires Validation)                         │
│ • Early-career users prioritize decision confidence over mass volume. │
│ • Explainable fit breakdown improves candidate time allocation.       │
│ • Structured gap identification reduces job application anxiety.       │
└────────────────────────────────────────────────────────────────────────┘
```

---

## Problem Hypotheses

* **Hypothesis 1 (Decision Bottleneck)**: Early-career candidates spend more time deciphering whether they qualify for roles than they do preparing high-quality applications `[HYPOTHESIS]`.
* **Hypothesis 2 (Explainability Value)**: Providing transparent, dimension-level fit reasoning (matching skills, partial overlaps, and missing requirements) will increase candidate application selectivity and reduce search fatigue `[HYPOTHESIS]`.
* **Hypothesis 3 (Centralization Value)**: Consolidating job discovery, fit evaluation, and tracking into a single decision loop will reduce workflow fragmentation friction `[HYPOTHESIS]`.

---

## Refined Problem Statement

> **"Early-career job seekers face high cognitive overload and decision paralysis when navigating unstructured job descriptions across fragmented platforms. Because they lack explainable mechanisms to evaluate how their academic and project experience aligns with employer requirements, candidates waste limited time on misaligned applications, experience search fatigue, and struggle to identify high-conviction opportunities."**

---

## Why This Problem Matters

1. **High-Stakes Transition**: The transition from academia to the first full-time role sets early career trajectory and earnings baseline `[DESK RESEARCH]`.
2. **Asymmetric Market**: Entry-level hiring has become hyper-competitive in tech and analytics; indiscriminate application volume yields diminishing returns while strategic alignment yields higher conversion `[PRODUCT INFERENCE]`.
3. **Unaddressed Gap**: Major job platforms optimize for employer listing revenue and candidate volume, leaving candidate-side decision support and explainable evaluation largely unaddressed `[PRODUCT INFERENCE]`.
