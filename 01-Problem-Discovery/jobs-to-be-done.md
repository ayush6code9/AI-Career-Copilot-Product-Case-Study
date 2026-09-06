# Jobs to Be Done (JTBD) Framework

This framework evaluates early-career candidate hiring behaviors through customer jobs: the core progress users are attempting to make when navigating job markets.

---

## 1. Job Classification Overview

```
                           ┌─────────────────────────────────────────┐
                           │            CORE PROGRESS GOAL           │
                           │ "Secure a high-fit entry-level role     │
                           │  without burning out on low-signal jobs"│
                           └────────────────────┬────────────────────┘
                                                │
         ┌──────────────────────────────────────┼──────────────────────────────────────┐
         ▼                                      ▼                                      ▼
┌──────────────────┐                  ┌──────────────────┐                   ┌──────────────────┐
│ FUNCTIONAL JOBS  │                  │  EMOTIONAL JOBS  │                   │   SOCIAL JOBS    │
│ • Filter listings│                  │ • Gain confidence│                   │ • Project        │
│ • Compare skills │                  │ • Reduce anxiety │                   │   competence to  │
│ • Track status   │                  │ • Avoid fatigue  │                   │   peers & family │
└──────────────────┘                  └──────────────────┘                   └──────────────────┘
```

* **Functional Jobs**: The objective operational tasks the user needs to execute (e.g., assessing qualification match, organizing deadlines, identifying missing skills).
* **Emotional Jobs**: How the user wants to feel during and after the process (e.g., feeling confident in their application choices, in control of their search, free from imposter syndrome).
* **Social Jobs**: How the user wants to be perceived by their peers, mentors, and employers (e.g., seen as a strategic, highly qualified professional rather than a desperate applicant).

---

## 2. Core Job Statements (5–7 Structured JTBDs)

### JTBD 1: Explainable Fit Assessment (Core Functional Job)
> **"When** I find a new entry-level job posting with an extensive list of requirements,  
> **I want to** instantly see a clear breakdown of how my skills and projects align with the role,  
> **so I can** determine whether this opportunity is genuinely worth my time to pursue.**"**

* **Trigger**: Encountering an appealing job listing with ambiguous or lengthy qualifications `[ASSUMPTION]`.
* **Desired Outcome**: An objective, transparent evaluation of strong matches, partial overlaps, and missing requirements `[PRODUCT INFERENCE]`.
* **Current Solution**: Manually skimming the JD and guessing fit, or copy-pasting into a generic LLM prompt `[FACT]`.
* **Friction**: Generic LLMs lack persistent candidate profile context; manual skimming causes self-doubt and misjudgment `[PRODUCT INFERENCE]`.
* **Opportunity**: Provide structured, explainable match summaries linked directly to the candidate's profile `[PRODUCT INFERENCE]`.

---

### JTBD 2: Opportunity Prioritization (Decision-Support Job)
> **"When** I have accumulated dozens of open job tabs across multiple job boards,  
> **I want to** rank and group opportunities into clear priority tiers (e.g., Strong Fit, Stretch, Low Match),  
> **so I can** focus my limited weekly hours on the highest-yield applications first.**"**

* **Trigger**: A search session resulting in 30+ open tabs and feeling overwhelmed by choice `[ASSUMPTION]`.
* **Desired Outcome**: A prioritized, ranked queue of roles ordered by match quality and urgency `[ASSUMPTION]`.
* **Current Solution**: Applying chronologically in the order tabs were opened, or picking recognizable brand names first `[ASSUMPTION]`.
* **Friction**: High effort spent on low-probability roles; high-fit opportunities slip past application deadlines `[PRODUCT INFERENCE]`.
* **Opportunity**: Algorithmic sorting based on explainable qualification compatibility `[PRODUCT INFERENCE]`.

---

### JTBD 3: Actionable Skill-Gap Clarification (Learning / Growth Job)
> **"When** an opportunity requires skills or tools I haven't fully used before,  
> **I want to** understand whether the gap is a critical blocker or a secondary requirement I can address quickly,  
> **so I can** decide whether to apply anyway, adapt my project narrative, or upskill.**"**

* **Trigger**: Seeing a job that matches 70% of profile but lists 1–2 unfamiliar frameworks `[ASSUMPTION]`.
* **Desired Outcome**: Clear distinction between hard prerequisites vs. learnable-on-the-job tools `[PRODUCT INFERENCE]`.
* **Current Solution**: Self-selecting out and abandoning the application, or applying blindly without addressing the gap `[ASSUMPTION]`.
* **Friction**: Unnecessary candidate drop-off due to inflated JD wording `[DESK RESEARCH]`.
* **Opportunity**: Surface gap severity (e.g., Core Requirement vs. Preferred Tool) and recommended next action `[PRODUCT INFERENCE]`.

---

### JTBD 4: Contextual Narrative Alignment (Application Enablement Job)
> **"When** I decide to apply for a prioritized high-fit role,  
> **I want to** identify which of my specific academic/portfolio projects are most relevant to highlight,  
> **so I can** submit an aligned, persuasive application without spending hours in manual guesswork.**"**

* **Trigger**: Moving a job opportunity from evaluation into the active application stage `[ASSUMPTION]`.
* **Desired Outcome**: Clear mapping between candidate's specific portfolio evidence and the JD's core duties `[ASSUMPTION]`.
* **Current Solution**: Maintaining 5+ resume files manually and guessing which project bullets to include `[ASSUMPTION]`.
* **Friction**: High cognitive overhead and inconsistent narrative positioning across applications `[PRODUCT INFERENCE]`.
* **Opportunity**: Contextual project-to-requirement mapping insights `[PRODUCT INFERENCE]`.

---

### JTBD 5: Centralized Application Intelligence (Workflow Job)
> **"When** an employer reaches out for an initial phone screen weeks after I applied,  
> **I want to** instantly retrieve the original job description, match analysis, and notes I used when applying,  
> **so I can** speak intelligently about the role without frantic searching.**"**

* **Trigger**: Receiving an email or phone call from a corporate recruiter for an interview `[FACT]`.
* **Desired Outcome**: Instant access to the historical snapshot of the exact JD, requirements, and candidate alignment notes `[ASSUMPTION]`.
* **Current Solution**: Searching Gmail for company name or clicking expired job board links `[FACT]`.
* **Friction**: Original job listings are often removed or archived by employers once applications close `[FACT]`.
* **Opportunity**: Snapshot and persist job metadata directly in an integrated pipeline tracker `[PRODUCT INFERENCE]`.

---

### JTBD 6: Emotional Control & Burnout Reduction (Emotional Job)
> **"When** I experience rejection or silence after submitting applications,  
> **I want to** have clear visibility into my pipeline health and conversion stages,  
> **so I can** maintain emotional resilience and adjust my strategy objectively rather than feeling defeated.**"**

* **Trigger**: Receiving automated rejection emails or experiencing multi-week silence `[ASSUMPTION]`.
* **Desired Outcome**: Transparent pipeline visibility showing application volume, response rates, and bottleneck stages `[ASSUMPTION]`.
* **Current Solution**: Internalizing rejection as personal failure and oscillating between mass-applying and inactivity `[ASSUMPTION]`.
* **Friction**: Opaque hiring funnels leave candidates with zero actionable feedback `[FACT]`.
* **Opportunity**: Clear tracking metrics that frame job search as an analytical funnel rather than an emotional ordeal `[PRODUCT INFERENCE]`.

---

## 3. Summary of JTBD Priorities

| JTBD # | Job Name | Primary Category | User Impact | Product Priority |
| :--- | :--- | :--- | :---: | :---: |
| **JTBD 1** | Explainable Fit Assessment | Functional / Cognitive | **Critical** | **P0 (MVP Core)** |
| **JTBD 2** | Opportunity Prioritization | Decision-Support | **Critical** | **P0 (MVP Core)** |
| **JTBD 5** | Centralized Application Intelligence | Operational / Workflow | **High** | **P0 (MVP Core)** |
| **JTBD 3** | Skill-Gap Clarification | Functional / Learning | **High** | **P1 (Near-Term)** |
| **JTBD 4** | Contextual Narrative Alignment | Enablement | **Medium** | **P1 (Near-Term)** |
| **JTBD 6** | Pipeline Health & Funnel Visibility | Emotional / Analytics | **Medium** | **P2 (Later Stage)** |
