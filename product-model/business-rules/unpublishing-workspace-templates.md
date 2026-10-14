---
appliesTo:
- type: entity
  id: workspace-template
  effect: removes
permits:
- related:
  - verb: publishes
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
  target: server/routes/workspaces.ts#workspaceRoutes
- kind: code
  role: implementation
  target: server/schemas.ts#canPublishWorkspaceTemplates
---

# Only a workspace's admins and owners unpublish its templates

A template reaches every member and every presentation started from it, so publishing it is for Admins and Owners; Members start from templates.
