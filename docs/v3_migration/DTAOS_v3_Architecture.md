# DTAOS v3 Architecture

## Execution model

```text
User Request
  ↓
AI Loader
  ↓
Kernel
  ↓
Dispatcher
  ↓
Knowledge Selection
  ↓
Engine Selection
  ↓
Workflow Execution
  ↓
Quality Gate
  ↓
Output / Archive / Decision Memory
```

## Core directories

- `kernel/`: executable OS policy, dispatching, quality gate, decision memory.
- `engines/`: role-based expert engines.
- `knowledge/`: stable business, technology, customer, market, product knowledge.
- `skills/`: reusable high-level capabilities.
- `workflows/`: repeatable work processes.
- `prompts/`: model-specific launch prompts.
- `templates/`: reusable output templates.
- `docs/v3_migration/`: audit, migration, architecture documentation.

## v3 upgrade objective

DTAOS v3 should make a new AI chat recover operational context by reading a small set of loader/kernel files first, then selectively loading relevant knowledge and engines.
