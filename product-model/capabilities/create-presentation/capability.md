---
availability:
- place: web::studio
- place: cli
domain: presentations
references:
- kind: code
  role: implementation
  target: src/pages/CreatePage.tsx#CreatePage
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/services/presentations.ts#createPresentation
- kind: code
  role: implementation
  target: server/schemas.ts#CreatePresentationSchema
- kind: code
  role: implementation
  target: cli/commands.ts#runCommand
- kind: doc
  role: intent
  target: docs/requirements/REQ001.md
---

# Create presentation

An organizer writes a new presentation, with or without an account, or creates one from a deck file on the command line.
