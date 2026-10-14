---
availability:
- place: web::studio
domain: presentations
references:
- kind: code
  role: implementation
  target: src/components/CollaboratorsDialog.tsx#CollaboratorsDialog
- kind: code
  role: implementation
  target: server/services/collaborators.ts#grantDeckAccess
- kind: doc
  role: intent
  target: docs/requirements/REQ075.md
---

# Share presentation

An organizer gives another registered account access to a presentation, to view it, comment on it or edit it.
