---
domain: presentations
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredDeckCollaboratorSchema
- kind: code
  role: implementation
  target: server/services/collaborators.ts#grantDeckAccess
---

# Collaborator

A presentation shared with one registered account, at a level that decides what that account may do with it.

## Information kept

- **Level** — Can view, Can comment or Can edit
- **Email** — the address of the account it is shared with
- **Shared at** — when it was shared
