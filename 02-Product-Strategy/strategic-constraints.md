# Strategic Constraints & Risk Mitigation

This document details the real-world operational, technical, behavioral, and structural constraints that bound the product strategy for **AI Career Copilot**, along with explicit risk mitigations.

---

## 1. Calibrated Qualification Ontology (Communicating AI Uncertainty)

> **Core Principle**: AI Career Copilot never presents an LLM-generated fit evaluation as absolute, infallible truth. 

To eliminate false precision and build candidate trust, the system classifies every extracted requirement and match signal into 6 standardized certainty categories:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   QUALIFICATION TAXONOMY & STATUS                      │
├──────────────────────┬─────────────────────────────────────────────────┤
│ 1. HARD REQUIREMENT  │ Explicit non-negotiable prerequisite (e.g. BS/MS│
│                      │ in technical field, legal work authorization).  │
├──────────────────────┼─────────────────────────────────────────────────┤
│ 2. STRONG MATCH      │ Direct, verified evidence in candidate profile   │
│                      │ (e.g., Python scripts, SQL project, published). │
├──────────────────────┼─────────────────────────────────────────────────┤
│ 3. TRANSFERABLE MATCH│ Academic or conceptual equivalent (e.g., PyTorch│
│                      │ knowledge mapping to TensorFlow preference).    │
├──────────────────────┼─────────────────────────────────────────────────┤
│ 4. PREFERRED SKILL   │ Listed as "bonus/nice-to-have"; non-blocker.    │
├──────────────────────┼─────────────────────────────────────────────────┤
│ 5. MISSING SKILL     │ Explicit requirement absent from candidate info.│
├──────────────────────┼─────────────────────────────────────────────────┤
│ 6. UNCLEAR / VAGUE   │ Ambiguous JD wording that cannot be reliably    │
│                      │ verified without candidate clarification.       │
└──────────────────────┴─────────────────────────────────────────────────┘
```

---

## 2. Key Strategic Constraints & Mitigations

| # | Constraint Dimension | Why It Exists | Product Implication | Key Risk | Potential Mitigation |
| :- | :--- | :--- | :--- | :--- | :--- |
| **C-01** | **Ambiguous Job Descriptions** | Recruiters copy-paste legacy templates, blending department wishlists with generic buzzwords `[DESK RESEARCH]`. | System cannot treat raw JD text as a pure mathematical truth. | Over-penalizing candidate on secondary wishlist keywords. | Programmatically decouple "Core Prerequisites" from "Preferred Stack"; highlight ambiguous terms explicitly `[PRODUCT INFERENCE]`. |
| **C-02** | **LLM Uncertainty & Hallucination** | LLMs can misinterpret domain nuances or invent candidate project details `[FACT]`. | Fit evaluations must be grounded strictly in candidate profile text and JD contents. | Misleading candidate into false confidence or premature rejection. | Strict JSON schema extraction, temperature zero for extraction, and citation links showing exact source text `[PRODUCT INFERENCE]`. |
| **C-03** | **Candidate Time Scarcity** | Final-year students have only 8–12 hours/week amidst exams and capstone projects `[ASSUMPTION]`. | Onboarding and daily triage must deliver value in <2 minutes. | High abandonment if the tool requires long manual questionnaires. | Instant resume/LinkedIn PDF parsing to auto-populate profile baseline in 1 step `[PRODUCT INFERENCE]`. |
| **C-04** | **Candidate Privacy & Data Security** | Resumes contain PII (names, phone numbers, locations, academic history) `[FACT]`. | Sensitive career data must be handled with strict privacy controls. | Candidate fear of data sharing or unauthorized recruitment contact. | Client-side privacy controls, no sharing of candidate data with third-party recruiters, clear data deletion options `[FACT]`. |
| **C-05** | **Job Posting Ephemerality** | Postings close unpredictably, and links break within 2–4 weeks `[FACT]`. | Live URLs cannot be relied upon for long-term reference. | Candidate loses job description context before interview phone screen. | Permanent snapshotting of parsed JD text and match breakdown upon saving `[PRODUCT INFERENCE]`. |
| **C-06** | **Cold-Start / Profile Incompleteness** | Candidates often have unstructured resumes missing key project details `[ASSUMPTION]`. | Initial match score may underestimate true candidate skills. | Candidate receives low fit scores due to unlisted skills. | "Profile Health" nudges that suggest specific projects or skills to document if unmentioned `[PRODUCT INFERENCE]`. |
| **C-07** | **Platform Dependency & Ingestion Limits** | Job boards restrict API access and implement anti-scraping policies `[FACT]`. | Product cannot rely solely on scraping third-party closed platforms. | Fragile data ingestion pipeline. | Hybrid ingestion: support direct JD text pasting, URL parsing where permitted, and curated open job board feeds `[PRODUCT INFERENCE]`. |
| **C-08** | **False Confidence in AI Decisions** | Candidates might blindly accept AI priority ranking without thinking `[ASSUMPTION]`. | The tool must reinforce candidate judgment rather than replacing it. | Candidate applies without reading the job or preparing narrative. | Require candidate confirmation step before archiving; present match as "Analysis" not "Decision" `[PRODUCT INFERENCE]`. |

---

## 3. Scope Boundary Enforcement

```
┌────────────────────────────────────────────────────────────────────────┐
│ BOUNDARY CHECKLIST                                                     │
├────────────────────────────────────────────────────────────────────────┤
│ • Do we scrape gated user logins?           ➔ NO (Respect TOS & Privacy)│
│ • Do we auto-submit applications?          ➔ NO (Anti-Spam / Quality)  │
│ • Do we guarantee job offers?              ➔ NO (Ethical Calibration) │
│ • Do we present AI fit as infallible?       ➔ NO (Calibrated Ontology) │
└────────────────────────────────────────────────────────────────────────┘
```
