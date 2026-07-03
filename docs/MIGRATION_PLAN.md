# Migration Plan — DTAOS v2 to v3

Branch: `v3-refactor`

## Principles

- Preserve `main`.
- Apply all changes through `v3-refactor`.
- Do not delete existing assets during the first migration stage.
- Convert empty placeholders into operational documents.
- Record any rename or relocation before applying it.

## Phase 1 — Audit Baseline

- Add `docs/REPOSITORY_AUDIT.md`.
- Classify 106 operational files.
- Confirm preserve / integrate / reinforce / move decisions.

## Phase 2 — Kernel Layer

Add:

```text
kernel/README.md
kernel/DISPATCHER.md
kernel/QUALITY_GATE.md
kernel/STATE_RECOVERY.md
```

Purpose:

- `BOOT.md` remains the recovery document.
- `AI_LOADER.md` remains the new-session prompt.
- `kernel/` handles request routing, knowledge selection, and output quality gates.

## Phase 3 — Loader Integration

- Clarify `README.md`, `docs/AI_LOADER.md`, and `docs/BOOT.md` roles.
- Keep `docs/NEXT.md` and `docs/PROJECT_STATUS.md` for now.
- Later consider `runtime/state` only after boot flow is stable.

## Phase 4 — Knowledge Refactor

Priority:

1. Correct GrapheneAll case path.
2. Reinforce company knowledge placeholders.
3. Reinforce NET and certification knowledge.
4. Reinforce GrapheneTex, Carbide, and Coating product knowledge.
5. Reinforce market knowledge.

## Phase 5 — Engine Layer

Add:

```text
engines/persona/README.md
engines/design_review/README.md
engines/business_review/README.md
engines/technical_review/README.md
engines/government_proposal/README.md
engines/presentation/README.md
```

## Phase 6 — Release Candidate

Merge to `main` only after:

- Boot chain is clear.
- Kernel documents exist.
- Engine index exists.
- Major placeholders are reinforced.
- A pull request has been reviewed.
