---
availability:
- place: web::studio
- place: web::signed-in
domain: presentations
references:
- kind: code
  role: implementation
  target: src/components/MoveToWorkspaceDialog.tsx#MoveToWorkspaceDialog
- kind: code
  role: implementation
  target: server/services/presentations.ts#setPresentationWorkspace
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
---

# Move presentation to workspace

An organizer hands a presentation their account owns to one of their workspaces.
