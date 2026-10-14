---
actors:
- organizer
access: authenticated
entryPoints:
- web: /workspaces
references:
- kind: code
  role: implementation
  target: src/pages/WorkspacesPage.tsx#WorkspacesPage
---

# Signed in

What an organizer reaches only with an account: their account settings and their workspaces.
