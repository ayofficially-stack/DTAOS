# DTAOS Kernel

The Kernel is the execution layer of DTAOS v3.

It does not replace `docs/BOOT.md` or `docs/AI_LOADER.md`. It sits after them and decides how each request should be handled.

## Execution Chain

```text
User Request
→ AI_LOADER
→ BOOT Recovery
→ Kernel
→ Dispatcher
→ Engine Selection
→ Knowledge Selection
→ Workflow Execution
→ Quality Gate
→ Output
```

## Kernel Responsibilities

1. Classify the user request.
2. Identify the active project or domain.
3. Select the minimum required Knowledge files.
4. Select the proper Engine.
5. Select or create a Workflow.
6. Apply Quality Gate before final output.
7. Preserve important decisions into Memory or Lessons when needed.

## Core Kernel Files

| File | Role |
|---|---|
| `DISPATCHER.md` | Routes requests to Engines, Knowledge, and Workflows |
| `QUALITY_GATE.md` | Defines final output review rules |
| `STATE_RECOVERY.md` | Defines how DTAOS resumes context in a new AI session |

## Operating Rule

The Kernel should load only the minimum necessary context first. It should not load the entire repository unless the task explicitly requires full-system audit or refactoring.
