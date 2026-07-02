# DTAOS Boot Recovery Specification

> Defines how DTAOS restores the current working state.

---

# Purpose

The purpose of BOOT is not simply to read documents.

Its purpose is to restore the exact execution state
of the current DTAOS workspace.

After BOOT, the AI should behave as if the previous session never ended.

---

# Recovery Priority

Recovery must follow this order.

1. Architecture
2. Current Execution State
3. Active Project
4. Decisions
5. Lessons
6. Domain Knowledge
7. Resume Action

---

# Reading Order

The recommended reading sequence is:

docs/

BOOT.md

↓

ARCHITECTURE.md

↓

NEXT.md

↓

PROJECT_STATUS.md

↓

knowledge/cases/

↓

knowledge/lessons/

↓

knowledge/

---

# Resume Rule

Resume Action must never be inferred.

Resume Action must always be read from

docs/NEXT.md

If NEXT.md is unavailable,

report it and continue initialization.

---

# Missing Files

Read only files that actually exist.

Never assume a file exists.

If a referenced file is missing,

report the missing file,

skip it,

and continue Boot Recovery.

---

# Validation

A successful Boot Recovery must restore:

- Current Architecture
- Current Sprint
- Active Project
- Latest Decisions
- Latest Lessons
- Current Resume Action

without requiring additional explanation from the user.

---

# Completion Condition

BOOT is complete only when
the AI can immediately continue
the next task without asking
what should be done next.