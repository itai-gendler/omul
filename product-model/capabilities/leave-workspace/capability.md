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

# Leave workspace

A member leaves a workspace, whatever their role.
