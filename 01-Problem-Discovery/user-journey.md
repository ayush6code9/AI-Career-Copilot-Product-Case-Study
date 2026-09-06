# Current State User Journey Mapping

This document maps the **Current As-Is Experience** of early-career candidates navigating the job market without AI Career Copilot. It reveals where cognitive bottlenecks, friction, and drop-offs occur today.

---

## Current State Journey Matrix

```
[1. DISCOVER] ──▶ [2. UNDERSTAND] ──▶ [3. EVALUATE] ──▶ [4. PRIORITIZE] ──▶ [5. APPLY/ACT] ──▶ [6. TRACK]
  Scrolling          Decoding JDs       Mental Math        Tab Triage         Manual Edits       Spreadsheets
  Multiple Boards    Bloated Stacks     Opaque Match       Paralysis          Generic Resumes    Broken Links
```

---

### Stage 1: DISCOVER
* **User Goal**: Identify open, entry-level job opportunities in their target discipline (e.g., Data Analyst, Junior ML Engineer).
* **User Actions**:
  * Logs into LinkedIn, Indeed, Handshake, and Google Jobs.
  * Inputs search queries: *"Junior Data Analyst"*, *"Entry Level Software Engineer"*, *"Associate Business Analyst"*.
  * Opens 20–30 job listing links in new browser tabs.
* **Questions in User's Mind**:
  * *"Are there any new postings today that I haven't already seen?"*
  * *"Is this actually an entry-level role, or will it demand 3+ years of commercial experience?"*
* **Pain Points**: Duplicate postings, outdated listings, misleading "Entry-Level" titles.
* **Existing Workaround**: Subscribing to multiple email alerts; manually opening every posting to scan minimum requirements.
* **Emotional State**: **Overwhelmed & Skeptical** — inundated with repetitive listings.
* **Opportunity**: Aggregate and filter listings by genuine qualification baseline rather than arbitrary job board title tags.

---

### Stage 2: UNDERSTAND
* **User Goal**: Comprehend the true day-to-day responsibilities and core technical stack of the job posting.
* **User Actions**:
  * Reads through dense paragraphs of corporate description, bulleted lists of 15+ skills, and generic qualification sections.
* **Questions in User's Mind**:
  * *"What is this role actually doing day-to-day?"*
  * *"Which of these 15 requirements are must-haves versus nice-to-haves?"*
  * *"Do my academic/capstone projects count toward their required experience?"*
* **Pain Points**: Unstandardized job descriptions, laundry-list qualification stacks, lack of distinction between core vs. preferred criteria.
* **Existing Workaround**: Copy-pasting JD text into general LLMs (ChatGPT) asking for a 3-bullet summary; asking peers on forums.
* **Emotional State**: **Confused & Uncertain** — unable to parse corporate jargon from essential prerequisites.
* **Opportunity**: Structural decomposition of JDs into standardized, clear requirement tiers (Core Competency, Preferred Tools, Domain Context).

---

### Stage 3: EVALUATE
* **User Goal**: Assess personal fit against the job's requirements objectively.
* **User Actions**:
  * Mentally compares their own resume/skills against the JD bullet points.
  * Looks at platform indicators (e.g., LinkedIn "How you match" badges).
* **Questions in User's Mind**:
  * *"Am I competitive for this role?"*
  * *"If I know Python and SQL but don't know Airflow, will my application get instantly rejected?"*
  * *"Why is the platform telling me I'm a 'Top Applicant' when I don't know the core framework?"*
* **Pain Points**: Opaque match scores, keyword-only ATS matchers, inability to evaluate project-level proof of competence.
* **Existing Workaround**: Guesswork; mental checklists; applying regardless of fit or abandoning out of self-doubt.
* **Emotional State**: **Anxious & Imposter-Prone** — fear of immediate automated rejection.
* **Opportunity**: Transparent, explainable fit scoring that highlights matched skills, partial overlaps, and non-critical gaps.

---

### Stage 4: PRIORITIZE
* **User Goal**: Decide which 5–10 opportunities to actively prepare and apply for during the current session.
* **User Actions**:
  * Reviews the 25+ browser tabs currently open.
  * Attempts to sort by deadline, perceived company prestige, or match gut-feeling.
* **Questions in User's Mind**:
  * *"Which of these jobs give me the highest probability of getting an interview?"*
  * *"Should I spend my evening applying to this 1 dream role or 5 safer roles?"*
* **Pain Points**: Cognitive fatigue; lack of objective sorting criteria; losing track of high-fit tabs among lower-value tabs.
* **Existing Workaround**: Chronological applying (applying to tab #1 through #10 until exhausted); bookmarking tabs that are later forgotten.
* **Emotional State**: **Fatigued & Paralysis** — cognitive depletion leading to arbitrary choices.
* **Opportunity**: Automated prioritization queue categorizing roles into actionable tiers (e.g., High Match, Stretch, Low Signal).

---

### Stage 5: APPLY / ACT
* **User Goal**: Submit a high-quality, targeted application aligned to the role.
* **User Actions**:
  * Navigates to employer career site (Workday, Greenhouse, Lever).
  * Manually fills in candidate details and uploads tailored resume/cover letter.
* **Questions in User's Mind**:
  * *"Which projects on my resume are most compelling for this specific team?"*
  * *"How can I clearly highlight my transferable skills for this role?"*
* **Pain Points**: Time-consuming manual tailoring (1–2 hours per application); tedious re-entering of resume fields in ATS portals.
* **Existing Workaround**: Keeping 5–10 slightly different PDF resumes in a local folder; or abandoning customization and submitting a single generic resume.
* **Emotional State**: **Frustrated & Impatient** — repetitive manual data entry with low perceived ROI.
* **Opportunity**: Provide actionable context and project alignment cues directly before the candidate submits on the employer portal.

---

### Stage 6: TRACK
* **User Goal**: Maintain accurate records of where, when, and with what materials they applied.
* **User Actions**:
  * Opens Google Sheets or Notion to log company, title, date, and link.
  * Checks email daily for confirmation messages or recruiter reach-outs.
* **Questions in User's Mind**:
  * *"Did that company ever reply to my application from 3 weeks ago?"*
  * *"When a recruiter calls, how do I quickly pull up the original JD if the link is now broken?"*
* **Pain Points**: High friction of manual logging; broken/expired JD URLs after postings close; zero visibility into aggregate funnel conversion.
* **Existing Workaround**: Notion boards maintained intermittently; searching email inbox by company name when contacted.
* **Emotional State**: **Disconnected & Helpless** — zero feedback loop from the hiring market.
* **Opportunity**: Centralized, unified application tracker that snapshots the job description and match analysis automatically.

---

## Summary: Primary Journey Breakdowns

```
┌──────────────────────────────────────────────────────────────────────────┐
│ MAJOR DROP-OFF POINTS IN CURRENT JOURNEY                                 │
├──────────────────────────────────────────────────────────────────────────┤
│ 1. [Discover ➔ Understand]                                              │
│    Dropout due to inflated experience prerequisites on entry titles.     │
│ 2. [Understand ➔ Evaluate]                                              │
│    Dropout due to imposter syndrome or opaque keyword matching.          │
│ 3. [Evaluate ➔ Prioritize]                                               │
│    Decisional paralysis across 30+ open tabs leading to burnout.         │
│ 4. [Track]                                                               │
│    Complete breakdown of tracking habits due to manual friction.        │
└──────────────────────────────────────────────────────────────────────────┘
```
