---
availability:
- place: web::studio
domain: presentations
references:
- kind: code
  role: implementation
  target: src/pages/HomePage.tsx#HomePage
- kind: code
  role: implementation
  target: server/services/presentations.ts#deletePresentation
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: doc
  role: intent
  target: docs/requirements/REQ146.md
---

# Delete presentation

An organizer permanently deletes a presentation and everything kept with it.
