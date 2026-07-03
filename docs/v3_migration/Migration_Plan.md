# DTAOS v3 Migration Plan

## Migration principle
- Do not delete existing knowledge.
- Separate OS execution layers from knowledge assets.
- Convert documents into a Loader → Kernel → Engine → Workflow → Quality Gate execution chain.

## Phase 1 — Preserve and stabilize
- Keep `README.md`, `docs/*`, `knowledge/*`, `skills/*`, `modules/*` intact.
- Exclude `.git` from delivered ZIP.
- Add audit and migration documentation under `docs/v3_migration/`.

## Phase 2 — Add execution layer
- Add `kernel/` with boot policy, dispatcher, and quality gate.
- Add `engines/` for persona, design, business, technical, government proposal, presentation, and sales review.
- Add loader prompts for ChatGPT, Claude Desktop, and Gemini.

## Phase 3 — Normalize project/case structure
- Migrate `knowledge/cases/P001_GrpaheneAll` to `knowledge/cases/P001_GrapheneAll`.
- Leave a deprecated pointer in the original typo path or preserve migration note in audit.

## Phase 4 — Connect mature assets
- Connect `skills/S001_Proposal` to `engines/government_proposal`.
- Connect `knowledge/technology/T001_Graphene_Platform` to `engines/technical_review`.
- Connect `knowledge/lessons/decisions` to `kernel/DECISION_MEMORY.md`.

## Phase 5 — Fill weak areas
- Expand `personas`, `prompts`, `templates`, and `workflows`.
- Add a Quality Gate checklist before final outputs.
