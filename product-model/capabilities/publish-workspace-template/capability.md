---
availability:
- place: web::signed-in
domain: workspaces
references:
- kind: code
  role: implementation
  target: src/components/PublishTemplateDialog.tsx#PublishTemplateDialog
- kind: code
  role: implementation
  target: server/services/workspace-templates.ts#publishWorkspaceTemplate
- kind: doc
  role: intent
  target: docs/requirements/REQ004.md
---

# Publish workspace template

A workspace admin or owner publishes one of the workspace's presentations as a template its members start from.
