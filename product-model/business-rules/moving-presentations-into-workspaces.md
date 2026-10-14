---
appliesTo:
- type: entity
  id: presentation
  effect: changes
  facts:
  - Workspace
  contexts:
  - place: web::studio::home
permits:
- related:
  - verb: owns
    entity: organizer
references:
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
---

# Only a presentation's owner moves it into a workspace

Only the account that owns a presentation hands it to a workspace, and only to a workspace where it may create presentations.
