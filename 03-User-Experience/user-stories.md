# User Stories (MVP Specification)

This document specifies the core user stories across the 5 functional modules of **AI Career Copilot**, mapped directly to Phase 1 JTBDs and prioritized using the MoSCoW framework (Must / Should / Could).

---

## 1. Candidate Profile

| Story ID | User Story | User Value | MoSCoW | Related Pain Point / JTBD |
| :--- | :--- | :--- | :---: | :--- |
| **US-CP-01** | **As a** final-year student,  <br>**I want to** upload my resume (PDF) and have my skills and projects automatically parsed,  <br>**so that I can** set up my profile baseline in under 60 seconds without manual data entry. | Minimizes onboarding friction and time investment. | **Must Have** | `PP-08` / `JTBD 1` |
| **US-CP-02** | **As an** early-career job seeker,  <br>**I want to** review and manually edit my extracted technical skills and project descriptions,  <br>**so that I can** ensure the AI has an accurate representation of my background. | Gives candidate full control and eliminates misparsing errors. | **Must Have** | `PP-04` / `JTBD 1` |
| **US-CP-03** | **As a** job seeker targeting specific paths,  <br>**I want to** specify my target role titles (e.g., Data Analyst, ML Engineer) and workplace preferences (Remote/Hybrid),  <br>**so that** fit evaluations are calibrated against my exact goals. | Prevents misaligned recommendations for irrelevant disciplines. | **Should Have** | `PP-01` / `JTBD 2` |
| **US-CP-04** | **As a** candidate with non-traditional projects,  <br>**I want to** paste GitHub repository URLs and project summaries directly into my profile,  <br>**so that** my code artifacts are recognized as valid qualification evidence. | Enables self-taught candidates to showcase proof of work. | **Could Have** | `PP-04` / `JTBD 4` |

---

## 2. Job Ingestion & Discovery

| Story ID | User Story | User Value | MoSCoW | Related Pain Point / JTBD |
| :--- | :--- | :--- | :---: | :--- |
| **US-JD-01** | **As a** candidate browsing external job boards,  <br>**I want to** paste raw job description text directly into the tool,  <br>**so that I can** immediately evaluate postings from any website or portal. | Universal compatibility with 100% of job boards. | **Must Have** | `PP-01` / `JTBD 1` |
| **US-JD-02** | **As a** busy student,  <br>**I want to** paste a job listing URL to automatically extract the job title, company, and JD text,  <br>**so that I can** save time during fast tab-triage sessions. | Reduces copy-paste friction. | **Should Have** | `PP-01` / `JTBD 1` |
| **US-JD-03** | **As a** candidate exploring new roles,  <br>**I want to** view a curated feed of verified entry-level listings aligned with my target roles,  <br>**so that I can** discover fresh opportunities without searching 5 separate sites. | Centralizes initial search exploration. | **Could Have** | `PP-01` / `JTBD 2` |

---

## 3. Job-Fit Analysis (Core Explainability Engine)

| Story ID | User Story | User Value | MoSCoW | Related Pain Point / JTBD |
| :--- | :--- | :--- | :---: | :--- |
| **US-FA-01** | **As a** candidate evaluating a complex JD,  <br>**I want to** see an explainable breakdown of Demonstrated Matches, Transferable Overlaps, and Missing Gaps,  <br>**so that I can** know exactly *why* I qualify rather than relying on a black-box percentage. | Eliminates imposter syndrome and guesswork. | **Must Have** | `PP-05` / `JTBD 1` |
| **US-FA-02** | **As an** applicant reviewing job criteria,  <br>**I want** missing skills to be categorized as "Blocker" vs. "Learnable on the Job",  <br>**so that I can** avoid self-selecting out of viable stretch opportunities. | Calibrates realistic barrier to entry. | **Must Have** | `PP-06` / `JTBD 3` |
| **US-FA-03** | **As a** candidate inspecting match conclusions,  <br>**I want to** click on any matched skill to see the exact resume bullet or project that justified the match,  <br>**so that I can** trust and verify the AI reasoning. | Builds auditability and transparent trust. | **Must Have** | `PP-05` / `JTBD 1` |
| **US-FA-04** | **As a** candidate reviewing an ambiguous posting,  <br>**I want** the system to flag when a JD is too vague or lacks sufficient technical details,  <br>**so that I don't** develop false confidence in low-signal postings. | Prevents false precision and builds credibility. | **Should Have** | `PP-03` / `JTBD 1` |
| **US-FA-05** | **As a** candidate preparing to submit,  <br>**I want** tailored recommendations on which specific portfolio projects to emphasize in my application,  <br>**so that I can** maximize narrative relevance. | Enhances application positioning. | **Should Have** | `PP-08` / `JTBD 4` |

---

## 4. Opportunity Prioritization

| Story ID | User Story | User Value | MoSCoW | Related Pain Point / JTBD |
| :--- | :--- | :--- | :---: | :--- |
| **US-PR-01** | **As a** student managing 20+ open job tabs,  <br>**I want to** view analyzed opportunities grouped into priority tiers (High Fit, Stretch, Low Match),  <br>**so that I can** focus my limited hours on the highest-conviction applications first. | Resolves tab triage paralysis and time dilution. | **Must Have** | `PP-07` / `JTBD 2` |
| **US-PR-02** | **As a** candidate planning a 2-hour application sprint,  <br>**I want to** filter and sort my priority queue by fit tier and date added,  <br>**so that I can** efficiently execute my top targets. | Optimizes session time management. | **Should Have** | `PP-07` / `JTBD 2` |
| **US-PR-03** | **As a** strategic job seeker,  <br>**I want to** manually override an AI priority tier (e.g., promote a Stretch role to Target),  <br>**so that** my personal passion and referral status are reflected in the queue. | Maintains complete candidate agency. | **Should Have** | `PP-07` / `JTBD 2` |

---

## 5. Application Tracking & Context Archival

| Story ID | User Story | User Value | MoSCoW | Related Pain Point / JTBD |
| :--- | :--- | :--- | :---: | :--- |
| **US-TR-01** | **As an** active applicant,  <br>**I want** every analyzed and saved job to permanently archive the original JD text,  <br>**so that I never** lose context when employers delete the live posting after closing. | Guarantees zero context loss during interview prep. | **Must Have** | `PP-09` / `JTBD 5` |
| **US-TR-02** | **As an** applicant progressing through hiring stages,  <br>**I want to** update application status across a simple Kanban board (Applied, Screening, Interview, Offer),  <br>**so that I can** track my pipeline in one place without manual spreadsheets. | Replaces broken spreadsheet maintenance. | **Must Have** | `PP-09` / `JTBD 5` |
| **US-TR-03** | **As a** candidate receiving an unexpected recruiter phone screen,  <br>**I want to** 1-click open an "Interview Context Cheat Sheet" with my matched projects and JD requirements,  <br>**so that I can** speak intelligently and confidently during the call. | Transforms tracking into high-yield interview prep. | **Should Have** | `PP-09` / `JTBD 5` |
| **US-TR-04** | **As a** reflective job seeker,  <br>**I want to** log simple notes and rejection stages,  <br>**so that I can** identify where in the funnel my applications encounter friction. | Provides objective pipeline visibility. | **Could Have** | `PP-09` / `JTBD 6` |
