# DTAOS State Recovery

State Recovery defines how DTAOS resumes work in a new AI session.

## 1. Recovery Goal

The goal is not to recreate the whole repository context. The goal is to restore the latest validated operating state with minimum context.

## 2. Recovery Order

When a new AI session starts, recover in this order:

```text
1. README.md
2. docs/AI_LOADER.md
3. docs/BOOT.md
4. docs/NEXT.md
5. docs/PROJECT_STATUS.md
6. Latest Decisions and Lessons
7. Active Project Case
8. Relevant Knowledge
9. Relevant Engine
10. Relevant Workflow
11. Quality Gate
```

## 3. Active Project Recovery

If the task is project-specific, find the active case folder and load:

```text
README.md
PROJECT_CONTEXT.md
DECISIONS.md
REVIEW.md
OUTPUTS.md
PROJECT_LOG.md
RETROSPECTIVE.md, if available
```

## 4. Decision Recovery Rule

Approved decisions override newly generated suggestions.

Examples:

- Editable PPT is preferred as the final sales-material format.
- HTML is an intermediate editorial prototype, not the final deliverable.
- Design work must prioritize alignment, hierarchy, spacing, and professional tone over decorative icons.
- Government proposals should target evaluator criteria, not merely fill forms.

## 5. Unknown State Rule

If the latest project state cannot be determined, do not guess. Ask for the specific file, project name, or current objective.

## 6. Write-back Rule

When a new durable decision is made, it should be written to one of:

```text
knowledge/lessons/decisions/
knowledge/cases/<Project>/DECISIONS.md
docs/CHANGELOG.md
```

Only durable decisions should be written back. Temporary drafting choices should remain in the active project log.
