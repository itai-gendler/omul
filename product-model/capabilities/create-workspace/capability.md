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
  target: server/services/workspaces.ts#createWorkspace
- kind: doc
  role: intent
  target: docs/requirements/REQ128.md
---

# Create workspace

A signed-in organizer creates a workspace and becomes its owner.
