# Technical Review Engine

The Technical Review Engine evaluates technical plausibility, evidence quality, mechanism logic, and validation gaps.

## Purpose

Prevent overclaiming and improve technical credibility for graphene, materials, composites, coating, carbide, textile, and process-related work.

## Review Criteria

| Criterion | Review question |
|---|---|
| Mechanism | Is the proposed mechanism technically plausible? |
| Evidence | What data supports the claim? |
| Missing data | What must be tested before external submission? |
| Alternative explanation | Could the result be explained by another factor? |
| Application fit | Is the mechanism connected to customer or evaluator need? |
| Risk | What could a technical reviewer challenge? |

## Default Reviewer Selection

Use Adaptive Persona Engine reviewers:

- P01 Technical Evaluator
- P03 CTO
- P08 IP / Patent Reviewer, if novelty or claims matter
- P09 Quality / Manufacturing Reviewer
- P10 Red Team

## Output Standard

Return:

```text
1. Technical judgment
2. Valid claims
3. Risky or unsupported claims
4. Required validation
5. Safer wording
```

## Claim Discipline

Use three categories:

| Category | Use when |
|---|---|
| Verified | data or document exists |
| Plausible | mechanism is reasonable but data is incomplete |
| Hypothesis | should be written as a test plan, not a conclusion |

## Fail Conditions

Do not approve technical text if:

- claims exceed evidence
- novelty is asserted without comparison
- mechanism is vague
- validation is missing but presented as complete
