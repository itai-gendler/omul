---
appliesTo:
- type: entity
  id: workspace-member
  facts:
  - Role
- type: capability
  id: change-workspace-member-role
- type: capability
  id: remove-workspace-member
- type: capability
  id: leave-workspace
references:
- kind: code
  role: implementation
  target: server/services/workspaces.ts#countWorkspaceOwners
---

# A workspace always keeps at least one owner

Demoting, removing or leaving that would leave a workspace without an Owner is refused.
