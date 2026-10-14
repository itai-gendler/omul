---
appliesTo:
- type: entity
  id: workspace-member
  effect: changes
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
---

# Only a workspace's admins and owners change roles, and only owners touch an owner's

An Owner changes any member's role; an Admin changes the role of a member who is not an Owner, and never to Owner.
