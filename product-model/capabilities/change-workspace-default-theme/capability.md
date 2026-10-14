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
  target: server/services/workspaces.ts#setWorkspaceDefaultTheme
- kind: doc
  role: intent
  target: docs/requirements/REQ086.md
---

# Change workspace default theme

A workspace's owner chooses the built-in theme new presentations in the workspace start in.
