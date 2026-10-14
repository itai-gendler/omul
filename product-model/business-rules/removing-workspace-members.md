---
appliesTo:
- type: entity
  id: workspace-member
  effect: removes
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
- related:
  - verb: holds
    entity: organizer
references:
- kind: code
  role: implementation
  target: server/routes/workspaces.ts#workspaceRoutes
---

# Admins and owners remove members, only owners remove owners, and anyone may leave

An Owner removes any member; an Admin removes a member who is not an Owner; every member may remove themselves, whatever their role.
