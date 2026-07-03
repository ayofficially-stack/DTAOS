# Adaptive Persona Engine

The Adaptive Persona Engine selects only the reviewers that are relevant to the current task.

## Purpose

Do not run all reviewers for every task. Select the most relevant 3 to 5 reviewers from the reviewer pool.

## Reviewer Pool

| ID | Reviewer | Primary lens |
|---|---|---|
| P01 | Technical Evaluator | technical validity and novelty |
| P02 | Commercialization Evaluator | market, business model, adoption |
| P03 | CTO | technical architecture and feasibility |
| P04 | Procurement Manager | purchase decision, supplier risk, cost |
| P05 | Industrial Design Director | visual hierarchy, premium tone, readability |
| P06 | Presentation Reviewer | narrative, flow, persuasion |
| P07 | Investor / Business Developer | scalability, growth, partnership value |
| P08 | IP / Patent Reviewer | patentability, freedom-to-operate, defensibility |
| P09 | Quality / Manufacturing Reviewer | validation, process, production risk |
| P10 | Red Team | objections, weak logic, credibility risks |

## Selection Rule

1. Classify the task type.
2. Identify the target audience or evaluator.
3. Select 3 to 5 reviewers.
4. Assign reviewer weights.
5. Run each review separately.
6. Resolve conflicts.
7. Return unified recommendations.

## Default Selections

| Task type | Recommended reviewers |
|---|---|
| Government proposal / NET | P01, P02, P03, P10 |
| Technical material | P01, P03, P08, P09, P10 |
| Sales sheet / brochure | P04, P05, P07, P10 |
| PPT / presentation | P05, P06, P07, P10 |
| Investment decision | P02, P07, P09, P10 |

## Output Format

```text
Selected Reviewers
- Pxx: reason

Common Findings
- ...

Conflicts
- ...

Top 3 Revisions
1. ...
2. ...
3. ...

Unified Recommendation
- ...
```

## Anti-noise Rule

If a reviewer is not relevant to the task, do not include that reviewer. More reviewers do not mean better review quality.
