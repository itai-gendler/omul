---
appliesTo:
- type: entity
  id: collaborator
- type: capability
  id: share-presentation
- type: capability
  id: add-workspace-member
references:
- kind: code
  role: implementation
  target: server/accounts.ts#findUserByEmail
---

# Presentations are shared, and members added, only with accounts already registered

Sharing a presentation or adding a workspace member names an account by its email address; an address nobody signed up with is refused and no invitation is sent.
