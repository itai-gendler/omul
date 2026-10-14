---
availability:
- place: web::signed-in
- place: web::studio
domain: workspaces
references:
- kind: code
  role: implementation
  target: src/pages/WorkspacePage.tsx#WorkspacePage
- kind: code
  role: implementation
  target: server/services/presentations.ts#createPresentation
- kind: code
  role: implementation
  target: server/services/workspaces.ts#defaultDeckThemeFor
---

# Create workspace presentation

A member creates a new presentation the workspace owns.
