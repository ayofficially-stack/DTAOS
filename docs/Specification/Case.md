# DTAOS Case Specification

> Define how project cases are organized, maintained, and connected within DTAOS.

---

# Purpose

A Case records the complete lifecycle of a project.

Cases preserve project context.

They do not preserve reusable knowledge.

Reusable knowledge belongs to Lessons, Decisions, Workflows, Technologies, or Templates.

---

# Philosophy

A project validates knowledge.

A Case records the project.

A Lesson preserves the rule.

A Decision preserves the direction.

A Technology preserves the domain knowledge.

A Template preserves reusable assets.

A Case is temporary.

Knowledge is permanent.

---

# Case Lifecycle

Idea

↓

Planning

↓

Execution

↓

Review

↓

Retrospective

↓

Knowledge Extraction

↓

Archive

---

# Required Documents

Every Case should contain the following documents.

README.md

Project overview.

---

PROJECT_CONTEXT.md

Project background and objectives.

---

DECISIONS.md

Project-specific decisions.

Reference permanent Decisions whenever possible.

---

REVIEW.md

Review history during execution.

---

OUTPUTS.md

Deliverables produced by the project.

---

PROJECT_LOG.md

Chronological execution log.

---

RETROSPECTIVE.md

Final project review.

Summarize what should become reusable knowledge.

Do not duplicate Lessons.

Reference them instead.

---

# Writing Principles

A Case records

what happened.

It does not define standards.

A Case should describe

- objectives
- execution
- outputs
- review
- retrospective

Reusable knowledge must be extracted into the appropriate knowledge area.

---

# Relationship

Case

↓

Retrospective

↓

Lessons

↓

Workflow

↓

Technology

↓

Templates

Projects generate knowledge.

Cases do not own knowledge.

---

# Boot Recovery

When an Active Project exists,

BOOT should restore the project by reading:

1. README.md
2. PROJECT_CONTEXT.md
3. DECISIONS.md
4. REVIEW.md
5. OUTPUTS.md
6. PROJECT_LOG.md
7. RETROSPECTIVE.md

Read only existing files.

Never assume missing documents.

---

# Completion Rule

A Case is complete only when

- Deliverables are finalized.
- Retrospective is written.
- Lessons are extracted.
- Decisions are updated.
- Related Technologies are updated.
- Related Templates are updated.

Only then may the Case be archived.

---

# Quality Standard

A completed Case should allow another AI or another person to understand

- why the project existed,
- what was produced,
- how it evolved,
- what knowledge was created,

without requiring additional explanation.

---

# Goal

Cases preserve projects.

Knowledge evolves beyond projects.

DTAOS grows by extracting reusable knowledge from every completed Case.