# DTAOS Dispatcher

The Dispatcher routes each request to the correct Engine, Knowledge, Workflow, and Module.

## 1. Routing Principle

Do not answer directly before routing. First classify the request.

```text
Request
→ Domain
→ Active Project
→ Required Knowledge
→ Required Engine
→ Required Workflow
→ Quality Gate
```

## 2. Domain Routing Table

| User request type | Primary Engine | Required Knowledge | Workflow |
|---|---|---|---|
| Government project / NET / proposal | `engines/government_proposal` | `skills/S001_Proposal`, `knowledge/certifications`, related technology | Proposal workflow |
| Sales sheet / brochure / white-label material | `engines/design_review`, `engines/business_review` | `knowledge/company`, `knowledge/products`, `knowledge/lessons/Editorial` | Sales/PPT workflow |
| Technical review | `engines/technical_review` | `knowledge/technology`, product-specific files | Technical review workflow |
| Persona validation | `engines/persona` | `personas`, relevant project context | Persona review workflow |
| Presentation / PPT / slide planning | `engines/presentation`, `engines/design_review` | Design lessons, active project case | Presentation workflow |
| Investment / portfolio | `modules/wealth` | portfolio data, decision log | Wealth workflow |
| Learning / exam preparation | `modules/learning` | learning module | Learning workflow |
| Daily operating task | `modules/daily` | current state and relevant module | Daily workflow |

## 3. GrapheneAll Default Context

When the request mentions GrapheneAll, GrapheneTex, graphene, NET, carbide, coating, government proposal, or technical sales, load context in this order:

1. `docs/BOOT.md`
2. `docs/AI_LOADER.md`
3. `kernel/README.md`
4. Active project status from `docs/NEXT.md` and `docs/PROJECT_STATUS.md`
5. Relevant Knowledge files only
6. Relevant Engine
7. Quality Gate

## 4. Anti-overload Rule

The Dispatcher must avoid loading the full repository unless the request is explicitly about repository audit, migration, or system refactoring.

## 5. Output Rule

At the end of a routed task, the output should state the applied Engine and Workflow only when useful. For ordinary user-facing writing, do not expose internal routing unless requested.
