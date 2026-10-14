---
appliesTo:
- type: entity
  id: workspace
  effect: changes
permits:
- related:
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
  target: server/routes/workspaces.ts#workspaceRoutes
- kind: code
  role: implementation
  target: server/schemas.ts#canAdministerWorkspace
---

# Only a workspace's owner renames it or changes its default theme

Changing the workspace itself is for its Owners; Admins and Members are refused.
