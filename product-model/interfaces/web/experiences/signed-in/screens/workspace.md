---
entities:
- entity: workspace
  shows:
  - Name
  - Default theme
  collects:
  - Name
  - Default theme
- entity: workspace-member
  shows:
  - Name
  - Email
  - Role
  - Added at
  collects:
  - Email
  - Role
- entity: presentation
  shows:
  - Title
  - Join code
  - Created at
- entity: workspace-template
  shows:
  - Title
  - Description
  - Category
  - Tags
  - Published by
  - Published at
  collects:
  - Title
  - Description
  - Category
  - Tags
entryPoints:
- web: /workspaces/{id}
references:
- kind: code
  role: implementation
  target: src/pages/WorkspacePage.tsx#WorkspacePage
- kind: code
  role: implementation
  target: src/components/PublishTemplateDialog.tsx#PublishTemplateDialog
---

# Workspace

One workspace: its presentations, its published templates and its members.
