# User Personas

This document outlines 2 distinct archetypes within the primary target user segment. All persona characteristics are structured based on workflow observations and market mechanics, and are explicitly labeled as `[ASSUMPTION]` where behavioral tendencies are modeled.

---

## Primary Persona: The Final-Year Technical Graduate

### Archetype: "The Overwhelmed Aspiring Analyst / Engineer"

| Attribute | Profile Details | Evidence Class |
| :--- | :--- | :-: |
| **Persona Tag** | **Aarav — Final-Year Engineering / Analytics Senior** | `[ASSUMPTION]` |
| **Career Stage** | 4th-year Undergraduate (Computer Science / Data / Information Systems), actively seeking first full-time role. | `[FACT]` |
| **Target Roles** | Data Analyst, Product Analyst, Junior AI/ML Engineer, Software Engineer. | `[FACT]` |
| **Academic & Skill Baseline** | Python, SQL, foundational Machine Learning coursework, academic capstone projects, self-guided portfolio on GitHub. | `[ASSUMPTION]` |
| **Time Availability** | 8–12 hours per week dedicated to job search (balanced against coursework, exams, and capstone deadlines). | `[ASSUMPTION]` |

#### Goals & Motivations
* **Primary Goal**: Secure a full-time, role-aligned offer in data/analytics or software engineering before graduation `[ASSUMPTION]`.
* **Motivations**: Start career in a role that offers technical learning, structured mentorship, and stable career growth `[ASSUMPTION]`.
* **Underlying Anxiety**: Fear of graduating without an offer; anxiety caused by rejecting auto-emails and ambiguous job requirement checklists `[ASSUMPTION]`.

#### Behaviors & Current Workflow
1. **Search**: Browses LinkedIn, Handshake, and job alerts daily across multiple open browser tabs `[ASSUMPTION]`.
2. **Review**: Scans job descriptions to check years-of-experience requirements; often gets discouraged by 2+ year requirements on entry-level titles `[ASSUMPTION]`.
3. **Application**: Alternates between spending 2 hours customizing a single resume and submitting 20 quick-apply applications when feeling stressed `[ASSUMPTION]`.
4. **Tracking**: Keeps an inconsistent spreadsheet or relies on email notifications to recall where applications were sent `[ASSUMPTION]`.

#### Main Pain Points
* Inability to evaluate whether non-commercial project experience counts toward listed JD requirements `[PRODUCT INFERENCE]`.
* High cognitive fatigue deciding which 5 jobs to prioritize out of 40 open listings `[ASSUMPTION]`.
* Lack of actionable feedback on *why* certain applications receive no response `[FACT]`.

#### Constraints & Decision Criteria
* **Constraints**: Limited commercial experience; heavy academic schedule constraining hours available per day `[FACT]`.
* **Decision Criteria for Applying**: Role relevance (does the role match skills?), company credibility, and achievable barrier to entry `[ASSUMPTION]`.

#### Existing Tools & Workarounds
* **Job Search**: LinkedIn, Indeed, Handshake, Glassdoor `[FACT]`.
* **Analysis / Drafting**: Ad-hoc LLM prompting (pasting JDs into ChatGPT asking "am I qualified?") `[ASSUMPTION]`.
* **Organization**: Google Sheets, browser bookmarks, email search `[FACT]`.

#### What Success Looks Like for this Persona
* Spending <15 minutes per session to discover high-conviction roles.
* Clear understanding of why a job is categorized as High Match vs. Stretch.
* Explicit identification of addressable skill gaps before submitting an application.

---

## Secondary Persona: The Recent STEM Graduate / Early Pivot

### Archetype: "The Self-Taught Cross-Disciplinary Job Seeker"

| Attribute | Profile Details | Evidence Class |
| :--- | :--- | :-: |
| **Persona Tag** | **Priya — Recent Graduate (< 6 Months Post-Grad)** | `[ASSUMPTION]` |
| **Career Stage** | Graduated with non-CS STEM degree (e.g., Mathematics, Economics, Electrical Engineering); transitioned into Data & Product Analytics through self-study and bootcamps. | `[ASSUMPTION]` |
| **Target Roles** | Business Analyst, Product Analyst, Junior Data Scientist, Operations Analyst. | `[FACT]` |
| **Academic & Skill Baseline** | Strong analytical problem-solving, SQL, Tableau/PowerBI, basic Python, domain knowledge in business or economics. | `[ASSUMPTION]` |
| **Time Availability** | 20–30 hours per week in full-time job hunt mode. | `[ASSUMPTION]` |

#### Goals & Motivations
* **Primary Goal**: Land an entry-level analytical role where transferable quantitative skills are recognized and valued `[ASSUMPTION]`.
* **Motivations**: Validate the self-directed learning investment; secure financial independence `[ASSUMPTION]`.
* **Underlying Anxiety**: Fear of being screened out by automated ATS filters due to non-traditional major or lack of explicit formal internship `[ASSUMPTION]`.

#### Behaviors & Current Workflow
1. **Search**: Searches broad keywords ("Junior Analyst", "Associate Data Analyst", "Product Analyst") yielding hundreds of mixed-quality results `[ASSUMPTION]`.
2. **Review**: Experiences high uncertainty regarding whether domain knowledge compensates for partial gaps in specific tooling `[ASSUMPTION]`.
3. **Application**: Manually adjusts resume summary and project bullets across multiple saved Google Docs `[ASSUMPTION]`.
4. **Tracking**: Manages a complex Notion board with stages (Saved, Applied, Screening, Rejected), requiring heavy manual upkeep `[ASSUMPTION]`.

#### Main Pain Points
* High friction in determining if a company's "requirements" are hard prerequisites or flexible preferences `[PRODUCT INFERENCE]`.
* Difficulty highlighting portfolio projects effectively against diverse role descriptions `[ASSUMPTION]`.
* Loss of context when recruiters reach out weeks later and the original job posting has expired `[FACT]`.

#### Constraints & Decision Criteria
* **Constraints**: Non-traditional degree pathway for tech roles; heightened sensitivity to time-to-hire `[ASSUMPTION]`.
* **Decision Criteria for Applying**: Willingness of employer to evaluate portfolio projects; clarity of daily responsibilities `[ASSUMPTION]`.

#### Existing Tools & Workarounds
* **Job Search**: LinkedIn, Wellfound (AngelList), Indeed, company portals `[FACT]`.
* **Organization & Notes**: Notion, Google Docs `[FACT]`.

#### What Success Looks Like for this Persona
* Immediate clarity on which of her transferable skills match the JD and which technical gaps are critical.
* An organized, persistent repository of applied job descriptions and matching insights.

---

## Comparison of Persona Needs

| Persona Dimension | Primary (Aarav - Final Year Senior) | Secondary (Priya - Recent Grad / Pivot) |
| :--- | :--- | :--- |
| **Core Scarcity** | **Time & Focus** (Balancing coursework with high-conviction job hunt) `[ASSUMPTION]` | **Clarity & Calibration** (Evaluating how non-standard background maps to JDs) `[ASSUMPTION]` |
| **Primary Risk** | Wasting scarce hours on low-probability applications `[ASSUMPTION]` | Disqualification due to poor positioning of transferable skills `[ASSUMPTION]` |
| **Critical Product Need** | Automated job-fit prioritization & rapid evaluation `[PRODUCT INFERENCE]` | Explainable qualification breakdown & project alignment `[PRODUCT INFERENCE]` |
