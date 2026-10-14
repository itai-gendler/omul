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
  target: server/services/workspaces.ts#removeWorkspaceMember
---

# Remove workspace member

A workspace admin or owner removes someone from the workspace.
