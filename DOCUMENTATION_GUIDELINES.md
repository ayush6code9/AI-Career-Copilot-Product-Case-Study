# Product Documentation Guidelines

To maintain senior-level Product Management quality and avoid generic AI filler, all artifacts in this case study adhere to the following principles.

---

## 1. Information Classification Standard

Every claim, assertion, and insight must be explicitly tagged or contextualized using these five categories:

| Tag | Category | Definition |
| :--- | :--- | :--- |
| `[FACT]` | **Fact** | Verified ground truth (e.g., publicly documented platform mechanics, published industry API limits). |
| `[DESK RESEARCH]` | **Desk Research** | Publicly accessible reports, benchmark papers, industry documentation, or job portal structural data. |
| `[ASSUMPTION]` | **Assumption** | Unvalidated premise about user behavior or technical constraints required to scope the product. |
| `[HYPOTHESIS]` | **Hypothesis** | A testable statement stating expected outcomes under specific interventions. |
| `[PRODUCT INFERENCE]` | **Product Inference** | Logical deduction derived by combining facts, desk research, and product trade-offs. |

---

## 2. Core Quality Rules

1. **Zero Synthetic Validation**: Never manufacture fake user interview quotes, fake survey response counts (e.g., "78% of 200 surveyed users"), or simulated customer satisfaction scores.
2. **Explicit Decision Rationales ("Why this decision?")**: For every scoped feature, prioritized item, or architectural choice, articulate the exact trade-off made and why alternatives were rejected.
3. **Structured & Scannable**: Prefer clear tables, markdown alert callouts, and numbered lists over verbose narrative blocks.
4. **Interview-Ready Conciseness**: Write artifacts so a Hiring Manager or Head of Product can rapidly evaluate PM competencies (analytical rigor, customer focus, business acumen, and technical depth).
5. **No Unsupported Sizing**: Do not provide arbitrary TAM/SAM/SOM numbers without documented top-down or bottom-up calculation logic and data sources.
