---
appliesTo:
- type: entity
  id: presentation
  effect: removes
permits:
- related:
  - verb: owns
    entity: organizer
- related:
  - verb: holds-edit-link-for
    entity: organizer
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
    is-not: Member
references:
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/schemas.ts#canAdministerWorkspaceDecks
---

# Only the owner, the edit link holder or a workspace admin deletes a presentation

Deleting stays with the presentation itself: its owner or whoever holds its edit link deletes it, and in a workspace an Admin or Owner does. An account it is shared with at Can edit, and a workspace's Member, help build it but do not delete it.

## Rationale

Deleting a presentation takes everything the room submitted to it with it.
