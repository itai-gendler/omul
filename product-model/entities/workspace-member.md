---
domain: workspaces
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredWorkspaceMemberSchema
- kind: code
  role: implementation
  target: server/services/workspaces.ts#addWorkspaceMember
---

# Workspace member

One account's membership of one workspace, at a role.

## Information kept

- **Role** — Member, Admin or Owner
- **Email** — the address of the member's account
- **Name** — the member's display name
- **Added at** — when the membership was made
