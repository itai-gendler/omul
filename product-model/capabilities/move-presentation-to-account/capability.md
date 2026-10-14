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
  target: server/services/presentations.ts#setPresentationWorkspace
---

# Move presentation to account

A workspace's owner moves one of its presentations out of the workspace and into their own account.
