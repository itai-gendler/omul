---
appliesTo:
- type: entity
  id: workspace
- type: capability
  id: delete-workspace
references:
- kind: code
  role: implementation
  target: server/routes/workspaces.ts#workspaceRoutes
---

# A workspace that owns presentations cannot be deleted

Its presentations are moved out or deleted first; deleting a workspace never deletes a presentation.
