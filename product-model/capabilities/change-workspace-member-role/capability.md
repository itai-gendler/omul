---
availability:
- place: web::signed-in
domain: workspaces
references:
- kind: code
  role: implementation
  target: src/components/WorkspaceRoles.tsx
- kind: code
  role: implementation
  target: server/services/workspaces.ts#setWorkspaceMemberRole
---

# Change workspace member role

A workspace admin or owner changes a member's role.
