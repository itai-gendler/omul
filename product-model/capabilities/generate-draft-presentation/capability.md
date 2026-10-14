---
availability:
- place: web::studio
references:
- kind: code
  role: implementation
  target: src/pages/GeneratePage.tsx#GeneratePage
- kind: code
  role: implementation
  target: server/routes/deck-generation.ts#createDeckGenerationRoutes
- kind: code
  role: implementation
  target: server/deck-generator.ts#createDeckGenerator
- kind: doc
  role: intent
  target: docs/requirements/REQ007.md
---

# Generate draft presentation

An organizer describes a session in a short prompt and gets a draft presentation, written by a language model, to edit. Offered while the deployment configures a language model provider.
