---
availability:
- place: web::signed-in
domain: workspaces
references:
- kind: code
  role: implementation
  target: src/pages/WorkspacePage.tsx#WorkspacePage
- kind: code
  role: implementation
  target: server/routes/workspaces.ts#workspaceRoutes
- kind: code
  role: implementation
  target: server/services/workspaces.ts#deleteWorkspace
---

# Delete workspace

A workspace's owner deletes a workspace that owns no presentations.
