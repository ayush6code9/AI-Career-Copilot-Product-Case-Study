# Prioritization Decision Log

This document records the foundational prioritization trade-offs, alternative evaluations, strategic rationales, and revisit triggers for **AI Career Copilot**.

---

## 1. Decision Log Architecture

```
┌────────────────────────────────────────────────────────────────────────┐
│                     PRIORITIZATION DECISION LOG                        │
├────────────────────────────────────────────────────────────────────────┤
│ PD-01: Fit Explainability Prioritized Over Global Job Crawlers         │
│ PD-02: 100% Reliable Raw Text Paste Prioritized Over URL Web Scrapers  │
│ PD-03: Grounded Evidence Tooltips Prioritized Over Animated UI Polish  │
│ PD-04: Integrated Snapshot Tracking Included in Core MVP Scope         │
│ PD-05: Strict and Permanent Exclusion of Automated Auto-Apply Bots     │
│ PD-06: Qualitative Fit Tiers Adopted Over Single Percentage Scores     │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 2. Structured Decision Records

### Decision PD-01: Fit Explainability Prioritized Over Global Job Crawlers
* **Context**: Should the team invest initial engineering cycles in building a broad job aggregation crawler or a deep qualification evaluation engine?
* **Alternatives Considered**:
  * *Option A*: Build a web crawler indexing 5,000+ entry-level tech jobs across multiple portals.
  * *Option B*: Build an intelligent JD parser and explainable fit evaluation engine for candidate-imported postings.
* **Evaluation**: Option A enters a crowded, commoditized market (competing with Google Jobs, Indeed) without solving candidate decision fatigue. Option B addresses the primary cognitive bottleneck (`PP-05`) `[PRODUCT INFERENCE]`.
* **Decision**: **Prioritize Fit Explainability (Option B).**
* **Rationale**: Early-career job seekers are not struggling to find jobs; they are drowning in unstructured listings they cannot evaluate. Delivering high-conviction decision support creates immediate defensible utility `[FACT]`.
* **Consequence**: Users must copy-paste external job listings into the tool during initial MVP testing.
* **Revisit Trigger**: Revisit building curated feed aggregation in Horizon 2 once the core evaluation engine demonstrates strong engagement and user retention.

---

### Decision PD-02: Raw Text Paste Prioritized Over URL Web Scraping
* **Context**: How should job descriptions be ingested into the platform during the first development sprint?
* **Alternatives Considered**:
  * *Option A*: Make live URL scraping the mandatory primary ingestion path.
  * *Option B*: Make raw text pasting the primary P0 path, building URL scraping as a P1 secondary enhancer.
* **Evaluation**: Option A suffers from high technical fragility due to anti-bot measures, login firewalls (LinkedIn/Handshake), and dynamic SPAs `[FACT]`. Option B guarantees 100% reliability with zero edge-case failures.
* **Decision**: **Prioritize Raw Text Ingestion as P0 (Option B).**
* **Rationale**: Onboarding drop-off spikes when external scrapers fail. Ensuring 100% ingestion reliability on day one protects candidate trust and prevents blocking downstream fit analysis `[PRODUCT INFERENCE]`.
* **Consequence**: Candidates execute a simple `Cmd+A ➔ Cmd+C ➔ Cmd+V` from external postings.
* **Revisit Trigger**: Promote URL scraping to primary status if automated headless browser infrastructure achieves >95% extraction reliability across major ATS platforms.

---

### Decision PD-03: Grounded Evidence Tooltips Prioritized Over Visual UI Polish
* **Context**: When allocating frontend sprint hours, should effort go toward rich animations/visual dashboards or granular evidence tooltips linking to resume text?
* **Alternatives Considered**:
  * *Option A*: Polished visual gauges, interactive circular match charts, and animated dashboard transitions.
  * *Option B*: Inspectable evidence citations citing exact candidate resume bullets and project repositories.
* **Evaluation**: Option A provides cosmetic delight but zero trust. Option B directly eliminates AI hallucination skepticism and prepares candidates for interviews `[PRODUCT INFERENCE]`.
* **Decision**: **Prioritize Grounded Evidence Citations as P0 (Option B).**
* **Rationale**: Candidate trust is fragile. Grounding every match assertion in verified candidate data is the single most critical factor for product credibility `[PRODUCT INFERENCE]`.
* **Consequence**: MVP UI adopts clean, functional typography and low-fidelity containers rather than complex chart animations.
* **Revisit Trigger**: Invest in advanced data visualization after core evidence-matching accuracy exceeds 90% in user testing.

---

### Decision PD-04: Integrated Snapshot Tracking Included in Core MVP Scope
* **Context**: Should application tracking be deferred to a separate tool (e.g., advising users to use Notion/Sheets) to reduce initial MVP footprint?
* **Alternatives Considered**:
  * *Option A*: Build only the standalone Fit Analyzer; export results to CSV/Notion.
  * *Option B*: Include a lightweight, integrated Kanban pipeline that snapshots full JD text upon saving.
* **Evaluation**: Option A causes severe workflow fragmentation (`PP-09`) and fails to solve the critical problem of broken/expired JD links when recruiters reach out weeks later `[FACT]`.
* **Decision**: **Include Snapshot Tracking in Core MVP (Option B).**
* **Rationale**: Storing immutable local JD snapshots closes the loop from discovery to interview preparation, transforming a one-off analysis tool into an indispensable daily workflow system `[PRODUCT INFERENCE]`.
* **Consequence**: Requires building basic local storage state management and Kanban column UI in MVP.
* **Revisit Trigger**: If user telemetry shows zero usage of the tracking pipeline post-evaluation, evaluate unbundling tracking into an optional module.

---

### Decision PD-05: Strict and Permanent Exclusion of Automated Auto-Apply Bots
* **Context**: Automated application submission bots (e.g., LazyApply) have viral short-term marketing appeal. Should AI Career Copilot support auto-applying?
* **Alternatives Considered**:
  * *Option A*: Build background browser automation to blast applications across Workday/Greenhouse portals.
  * *Option B*: Strictly enforce guided candidate submission on official employer portals.
* **Evaluation**: Option A floods recruiters with spam, damages candidate reputations, triggers ATS anti-bot IP bans, and leaves candidates unprepared for interview callbacks `[DESK RESEARCH]`. Option B maintains high candidate intent and interview readiness.
* **Decision**: **Permanently Reject Auto-Apply Bots (Option B).**
* **Rationale**: AI Career Copilot is fundamentally a **decision-support copilot**, not a spam automation tool. Our goal is to maximize application conversion and candidate conviction, not vanity submission volume `[PRODUCT INFERENCE]`.
* **Consequence**: Users must click out to official company portals to submit their applications.
* **Revisit Trigger**: Non-negotiable. This is an immutable strategic boundary.

---

### Decision PD-06: Qualitative Fit Tiers Adopted Over Numerical Match Scores
* **Context**: Should overall opportunity compatibility be summarized as a single percentage (e.g., "82%") or qualitative tiers (*Strong Fit*, *Stretch*, *Low Fit*)?
* **Alternatives Considered**:
  * *Option A*: Single composite percentage match score (0–100%).
  * *Option B*: 5 qualitative assessment tiers accompanied by 3-bucket requirement evidence.
* **Evaluation**: Option A creates false mathematical precision (e.g., candidate agonizing over 78% vs. 82%) without explaining *why* `[PRODUCT INFERENCE]`. Option B provides actionable strategic clarity.
* **Decision**: **Adopt Qualitative Fit Tiers (Option B).**
* **Rationale**: Percentage scores disguise critical qualitative differences (e.g., missing 1 fatal visa prerequisite vs. missing 1 minor 2-hour syntax tool). Qualitative tiers guide immediate decision-making `[PRODUCT INFERENCE]`.
* **Consequence**: UI strictly avoids percentage wheels and decimal rankings.
* **Revisit Trigger**: Revisit if user testing reveals candidates struggle to triage opportunities without a secondary sorting score.
