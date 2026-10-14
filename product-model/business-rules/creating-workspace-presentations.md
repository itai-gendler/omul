---
appliesTo:
- type: entity
  id: presentation
  effect: creates
  contexts:
  - place: web::signed-in::workspace
permits:
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
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/schemas.ts#canCreateWorkspaceDecks
---

# Only a workspace's members create presentations in it

A presentation the workspace owns is created only by a member of that workspace, at any role.
