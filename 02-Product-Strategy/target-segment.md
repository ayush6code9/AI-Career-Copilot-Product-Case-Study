# Target Segment & User Segmentation

This document establishes the strategic boundaries for the initial target customer profile, explicitly defining who we build for and who we intentionally exclude.

---

## 1. Segmentation Dimensions

To avoid generic definitions, early-career candidates are evaluated across 7 multidimensional axes:

| Segmentation Axis | Target Profile Boundary | Non-Target / Boundary Limit | Evidence Class |
| :--- | :--- | :--- | :-: |
| **1. Career Stage** | Final-year students (within 12 months of graduation) & recent graduates (< 1 year post-graduation). | Mid-career professionals (3+ years commercial experience) or 1st/2nd year underclassmen seeking short internships. | `[FACT]` |
| **2. Role Focus** | Technical, analytical, and data-centric disciplines: Data Analyst, Product Analyst, Business Analyst, AI/ML Engineer, Software Engineer, GenAI Developer. | Non-technical roles (Sales, Direct Customer Service, Hospitality, General Operations). | `[FACT]` |
| **3. Experience Level** | 0 to 1 year of formal commercial experience; holds academic projects, coursework, open-source contributions, or 1 internship. | Senior/Staff engineers, Lead analysts, Management roles requiring proven organizational leadership. | `[FACT]` |
| **4. Search Intensity** | Active Job Seekers (submitting 5–20 applications/week or reviewing jobs daily). | Passive browsers with no near-term hiring timeline. | `[ASSUMPTION]` |
| **5. Time Scarcity** | High time constraints (balancing final exams, capstone deliverables, part-time jobs with job applications: 8–15 hrs/week). | Full-time career changers with unlimited daily hours. | `[ASSUMPTION]` |
| **6. Profile Depth** | Structured portfolio evidence available (GitHub, course projects, SQL/Python scripts, academic transcripts). | Zero technical baseline or unstructured career seekers without defined domain skills. | `[ASSUMPTION]` |
| **7. Decision Friction** | High cognitive uncertainty regarding job description qualifications vs. personal project readiness. | Candidates with pre-existing return offers or confirmed institutional placement pipelines. | `[PRODUCT INFERENCE]` |

---

## 2. Ideal Customer Profile (ICP)

```
┌────────────────────────────────────────────────────────────────────────┐
│ IDEAL CUSTOMER PROFILE (ICP) SUMMARY                                   │
├────────────────────────────────────────────────────────────────────────┤
│ • Who: Final-year university student or recent STEM/business graduate. │
│ • Role Target: Entry-level Data / Product / Software / AI roles.       │
│ • Portfolio: 2–4 substantive projects, foundational code/tools, no     │
│   extensive corporate track record.                                    │
│ • Pain: Overwhelmed by 30+ open tabs, confused by inflated JD criteria,│
│   wasting time guessing fit or blasting generic resumes.               │
│ • Primary Job: Needs fast, explainable match evaluations to prioritize │
│   the top 5–10 high-probability applications weekly.                   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Segment Categorization & Inclusions

### Primary User: The Final-Year Technical & Analytical Senior
* **Profile**: 4th-year undergraduate or graduate student in Computer Science, Data Science, Information Systems, Statistics, or Quantitative Economics.
* **Why Included**:
  * Faces an immediate, non-negotiable graduation deadline (6–9 months out) `[FACT]`.
  * Possesses concrete project artifacts (GitHub repos, capstones, SQL/Python models) that can be matched against technical JDs `[FACT]`.
  * Suffers severe time constraints due to academic workload, making automated decision-support highly valuable `[ASSUMPTION]`.

### Secondary User: The Recent Cross-Disciplinary STEM Pivot (< 1 Year Post-Grad)
* **Profile**: Recent graduate from adjacent quantitative fields (Mathematics, Physics, Industrial Engineering, Economics) who has upskilled in SQL/Python/BI tools for analytics roles.
* **Why Included**:
  * Possesses high analytical aptitude but experiences high uncertainty translating academic math/economics projects to corporate analytics requirements `[ASSUMPTION]`.
  * Strongly benefits from explainable skill-gap decomposition and transferable skill validation `[PRODUCT INFERENCE]`.

---

## 4. Out-of-Scope Segments (Explicit Non-Targets)

| Segment | Rationale for Exclusion | Strategic Risk of Inclusion |
| :--- | :--- | :--- |
| **Experienced Professionals (3+ YOE)** | Experienced candidates have established corporate track records, recruiter networks, and standardized resumes where keyword matching is less ambiguous `[FACT]`. | Dilutes focus; experienced hiring relies heavily on domain pedigree and executive recruitment networks rather than entry-level project matching `[PRODUCT INFERENCE]`. |
| **Non-Technical / Creative Job Seekers** | Evaluating portfolio fit for Graphic Design, Copywriting, or Sales requires subjective aesthetic/soft-skill heuristics outside our structured technical ontology `[PRODUCT INFERENCE]`. | Dramatically increases domain ontology complexity and reduces LLM evaluation accuracy in MVP `[PRODUCT INFERENCE]`. |
| **Uncalibrated Mass-Applicants (Spam Seekers)** | Users looking purely for one-click mass submission bots to blast 500+ generic applications daily `[ASSUMPTION]`. | Conflicts directly with our core value proposition of high-conviction decision quality and ecosystem integrity `[PRODUCT INFERENCE]`. |
| **1st / 2nd Year Underclassmen (Exploration Stage)** | Underclassmen seeking exploratory summer internships lack foundational project depth and face different institutional recruitment cycles `[FACT]`. | Distracts from the acute, high-stakes full-time employment conversion loop `[PRODUCT INFERENCE]`. |

---

## 5. Summary of Segment Strategy

```
┌─────────────────────────────────────────────────────────────┐
│ FOCUS BOUNDARY:                                             │
│ Target Narrowly: Entry-Level Tech & Analytics Roles (0-1 YOE)│
│ Deliver Deep Value: Explainable Project-to-JD Evaluation    │
│ Avoid: Horizontal expansion across non-technical domains    │
└─────────────────────────────────────────────────────────────┘
```
