---
entities:
- entity: presentation
  shows:
  - Title
  - Join code
  - Created at
  - Owner
  - Workspace
- entity: collaborator
  shows:
  - Email
  - Level
  collects:
  - Email
  - Level
- entity: account
  shows:
  - Email verified
  collects:
  - Name
  - Email
  - Password
- entity: workspace
  shows:
  - Name
entryPoints:
- web: /app
references:
- kind: code
  role: implementation
  target: src/pages/HomePage.tsx#HomePage
- kind: code
  role: implementation
  target: src/components/CollaboratorsDialog.tsx#CollaboratorsDialog
- kind: code
  role: implementation
  target: src/components/MoveToWorkspaceDialog.tsx#MoveToWorkspaceDialog
---

# Home

The organizer's front door: the presentations this browser or account holds, those shared with the account, the ways to start a new one, and signing in.
