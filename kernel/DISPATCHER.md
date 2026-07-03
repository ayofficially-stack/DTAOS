# Dispatcher

## Routing rules

- Government project / NET / proposal → `engines/government_proposal` + `skills/S001_Proposal` + relevant technology knowledge.
- Sales sheet / brochure / PPT → `engines/design_review` + `engines/sales` + `workflows`.
- Technical review → `engines/technical_review` + `knowledge/technology`.
- Persona validation → `engines/persona`.
- Investment / portfolio → `modules/wealth`.
- Learning / exam prep → `modules/learning`.

The dispatcher should load only the minimum required context first, then request additional files if needed.
