---
appliesTo:
- type: entity
  id: presentation
  effect: changes
  facts:
  - Workspace
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
  when:
  - entity: workspace-member
    fact: Role
    is: Owner
references:
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/schemas.ts#canAdministerWorkspace
---

# Only a workspace's owner moves a presentation out of it

Taking a presentation out of a workspace ends the workspace's shared ownership of it, so only an Owner of that workspace does it.
