---
appliesTo:
- type: entity
  id: presentation
  effect: changes
permits:
- related:
  - verb: owns
    entity: organizer
- related:
  - verb: holds-edit-link-for
    entity: organizer
- related:
  - verb: has
    entity: collaborator
  - verb: holds
    entity: organizer
  when:
  - entity: collaborator
    fact: Level
    is: Can edit
- related:
  - verb: owns
    entity: workspace
  - verb: has
    entity: workspace-member
  - verb: holds
    entity: organizer
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#resolveDeckAccess
- kind: code
  role: implementation
  target: server/schemas.ts#canMutateDeck
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: doc
  role: intent
  target: docs/api.md
  title: Auth model
---

# Only a presentation's editors change it

A presentation's settings, its session and everything the presenter view controls are changed by its owner, whoever holds its edit link, an account it is shared with at Can edit, and every member of the workspace that owns it. Accounts it is shared with at Can view or Can comment read it as its editors do and change nothing.
