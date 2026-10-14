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
  target: server/services/workspaces.ts#addWorkspaceMember
- kind: doc
  role: intent
  target: docs/requirements/REQ129.md
---

# Add workspace member

A workspace admin or owner adds a registered account to the workspace at a role.
