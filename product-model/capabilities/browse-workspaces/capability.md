---
availability:
- place: web::signed-in
domain: workspaces
references:
- kind: code
  role: implementation
  target: src/pages/WorkspacesPage.tsx#WorkspacesPage
- kind: code
  role: implementation
  target: server/services/workspaces.ts#listWorkspacesForUser
---

# Browse workspaces

A signed-in organizer sees the workspaces they belong to, with their role in each.
