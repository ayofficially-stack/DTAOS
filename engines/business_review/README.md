# Business Review Engine

The Business Review Engine evaluates whether a technology, document, or sales material can create real customer action.

## Purpose

Translate technology into customer need, market logic, adoption path, and revenue potential.

## Review Criteria

| Criterion | Review question |
|---|---|
| Target customer | Who buys or adopts this? |
| Pain point | What dissatisfaction or operational problem is being solved? |
| Urgency | Why now? |
| Differentiation | Why this solution instead of existing alternatives? |
| Adoption path | What is the first PoC or purchase step? |
| Revenue path | How does this convert to sales or partnership? |
| Risk | What would stop the customer from moving forward? |

## Default Reviewer Selection

Use Adaptive Persona Engine reviewers:

- P02 Commercialization Evaluator
- P04 Procurement Manager
- P07 Investor / Business Developer
- P10 Red Team

## Output Standard

Return:

```text
1. Business strength
2. Weakness or missing evidence
3. Customer adoption risk
4. Commercialization logic
5. Recommended revision
```

## Fail Conditions

Do not mark a business case as strong if:

- target market is vague
- customer pain is generic
- revenue path is not explained
- differentiation depends only on broad claims
- PoC path is unclear
