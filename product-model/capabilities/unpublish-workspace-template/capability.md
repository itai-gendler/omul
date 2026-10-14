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
  target: server/services/workspace-templates.ts#unpublishWorkspaceTemplate
---

# Unpublish workspace template

A workspace admin or owner takes one of the workspace's templates down.
