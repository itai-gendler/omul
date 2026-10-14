---
appliesTo:
- type: entity
  id: workspace-member
  effect: creates
permits:
- related:
  - &id001
    verb: has
    entity: workspace
  - &id002
    verb: has
    entity: workspace-member
  - &id003
    verb: holds
    entity: organizer
  when:
  - entity: workspace-member
    fact: Role
    is: Owner
- related:
  - *id001
  - *id002
  - *id003
  when:
  - entity: workspace-member
    fact: Role
    is: Admin
  - fact: Role
    is-not: Owner
references:
- kind: code
  role: implementation
  target: server/routes/workspaces.ts#workspaceRoutes
- kind: code
  role: implementation
  target: server/schemas.ts#canManageWorkspaceMembers
---

# Only a workspace's admins and owners add members, and only owners add owners

An Owner adds a member at any role; an Admin adds Members and Admins.
