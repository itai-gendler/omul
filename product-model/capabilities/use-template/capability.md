---
availability:
- place: web::studio
- place: cli
domain: templates
references:
- kind: code
  role: implementation
  target: src/components/TemplateCard.tsx
- kind: code
  role: implementation
  target: server/templates.ts#copyTemplateSlides
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: doc
  role: intent
  target: docs/requirements/REQ006.md
---

# Use template

An organizer starts a new presentation from one of the prebuilt decks in the catalog.
