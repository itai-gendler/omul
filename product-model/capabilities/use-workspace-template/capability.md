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
  target: server/services/workspace-templates.ts#getWorkspaceTemplate
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
---

# Use workspace template

A member starts a new presentation of the workspace's from one of the templates the workspace publishes.
