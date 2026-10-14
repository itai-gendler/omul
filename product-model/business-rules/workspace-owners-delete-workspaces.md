---
appliesTo:
- type: entity
  id: workspace
  effect: removes
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
---

# Only a workspace's owner deletes it

Deleting a workspace is for its Owners.
