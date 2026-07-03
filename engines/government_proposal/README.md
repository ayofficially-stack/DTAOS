# Government Proposal Engine

The Government Proposal Engine supports NET, R&D, technology demand forms, certification documents, and government project proposals.

## Purpose

Write and review proposals from the evaluator's scoring perspective, not merely by filling the form.

## Inputs

- Announcement or application form
- Evaluation criteria
- Target technology
- Active project context
- Available evidence and missing evidence

## Knowledge to Load

```text
skills/S001_Proposal/
knowledge/certifications/
knowledge/technology/
knowledge/company/
knowledge/cases/<ActiveProject>/
knowledge/lessons/Proposal.md
```

## Default Reviewer Selection

Use Adaptive Persona Engine reviewers:

| Reviewer | Reason |
|---|---|
| P01 Technical Evaluator | novelty, advancement, technical validity |
| P02 Commercialization Evaluator | market, adoption, business model |
| P03 CTO | feasibility and implementation logic |
| P10 Red Team | evaluator objections and weak evidence |

Optional reviewers:

- P08 IP / Patent Reviewer if patentability or NET novelty is central.
- P09 Quality / Manufacturing Reviewer if validation, production, or process reliability is central.

## Workflow

```text
1. Define objective and evaluator perspective.
2. Extract scoring criteria.
3. Map claims to evidence.
4. Separate technology need from technology solution.
5. Draft or review by section.
6. Run Adaptive Persona Engine.
7. Apply Quality Gate.
8. Produce final text or revision plan.
```

## Output Standard

The output must include:

- evaluator-facing structure
- clear differentiation
- evidence discipline
- risk and mitigation
- copy-ready Korean text when requested

## Fail Conditions

Do not mark the work complete if:

- novelty is asserted without basis
- market need is generic
- missing data is hidden
- technology benefit is not linked to application or customer need
- writing sounds promotional rather than evaluative
