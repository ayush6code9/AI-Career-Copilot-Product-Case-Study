# UX Principles & Interaction Guidelines

These 6 UX principles govern the design system, interface layouts, and interaction patterns across **AI Career Copilot**.

---

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CORE UX PRINCIPLES                              │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Explain Before Recommending                                         │
│ 2. Ground Every Assessment in Visible Evidence                         │
│ 3. Never Hide or Disguise AI Uncertainty                               │
│ 4. Keep Candidate Agency at the Center of Execution                    │
│ 5. Turn Cognitive Analysis into Immediate Action                       │
│ 6. Minimize Input Overhead at Every Step                               │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 1. Explain Before Recommending

* **UX Meaning**: The interface must always present the structural rationale *before* showing a summary badge or action recommendation. Users should never see a conclusion without understanding the underlying logic.
* **Why It Matters**: Job seekers are naturally skeptical of automated matching. Displaying transparent reasons first establishes intellectual credibility `[PRODUCT INFERENCE]`.
* **Example Application**: On the Job-Fit card, the requirement breakdown (Demonstrated Matches, Transferable Overlaps, Gaps) is displayed prominently alongside the qualitative tier, with immediate expandable evidence accordions.

---

## 2. Ground Every Assessment in Visible Evidence

* **UX Meaning**: If the AI asserts that a candidate is a match for a skill, the UI must provide an inspectable visual citation linking directly to the candidate's verified profile data (resume bullet, project repo, coursework).
* **Why It Matters**: Prevents hallucinations and eliminates "black-box" skepticism `[FACT]`.
* **Example Application**: Hovering or clicking on *"SQL Match"* renders a subtle popover: *"Extracted from Resume: 'Built PostgreSQL data warehouse for Senior Capstone Project'"*.

---

## 3. Never Hide or Disguise AI Uncertainty

* **UX Meaning**: If a job description is vague, contradictory, or lacks technical depth, the UI must transparently state the system's limitation rather than guessing with false confidence.
* **Why It Matters**: Communicating ambiguity protects candidates from making bad decisions based on superficial AI assertions `[PRODUCT INFERENCE]`.
* **Example Application**: Low-confidence JDs display an amber warning badge: *"⚠️ Ambiguous Posting: Responsibilities are unstated. AI confidence is Low (45%). Please review the raw posting text."*

---

## 4. Keep Candidate Agency at the Center of Execution

* **UX Meaning**: The system is an analytical co-pilot, not an autonomous agent. Every critical state transition (prioritizing, applying, discarding, status progression) requires an explicit, intentional candidate click.
* **Why It Matters**: Keeps candidates mentally engaged and personally invested in their job search, ensuring high interview readiness `[PRODUCT INFERENCE]`.
* **Example Application**: Opportunities are suggested into priority tiers, but the candidate retains 1-click drag-and-drop capability to override tiers or customize personal notes.

---

## 5. Turn Cognitive Analysis into Immediate Action

* **UX Meaning**: Every analytical insight presented to the user must be immediately paired with a clear, low-friction next action. Analysis without action causes fatigue.
* **Why It Matters**: Early-career candidates suffer from paralysis; the interface must actively propel them toward productive execution `[ASSUMPTION]`.
* **Example Application**: When an analysis identifies a "Learnable Gap" (e.g., Docker CLI), the card immediately surfaces a 1-line preparation note and provides a direct CTA: *"Add to Priority Queue & Apply"*.

---

## 6. Minimize Input Overhead at Every Step

* **UX Meaning**: Deliver maximum value from minimal user input. Never ask the user to type information that can be reliably parsed from their existing resume or URL.
* **Why It Matters**: Form fatigue is the #1 cause of abandonment during onboarding and daily usage `[FACT]`.
* **Example Application**: 1-click resume PDF upload auto-extracts candidate baseline; pasting a job URL auto-fills title, company, and raw text.
