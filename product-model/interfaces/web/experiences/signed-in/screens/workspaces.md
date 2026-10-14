---
entities:
- entity: workspace
  shows:
  - Name
  collects:
  - Name
- entity: workspace-member
  shows:
  - Role
entryPoints:
- web: /workspaces
references:
- kind: code
  role: implementation
  target: src/pages/WorkspacesPage.tsx#WorkspacesPage
---

# Workspaces

The workspaces the signed-in person is a member of, and creating a new one.
