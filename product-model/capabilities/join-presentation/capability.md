---
availability:
- place: web::audience
domain: participation
references:
- kind: code
  role: implementation
  target: src/pages/JoinPage.tsx#JoinPage
- kind: code
  role: implementation
  target: server/routes/presentations.ts#presentationRoutes
- kind: code
  role: implementation
  target: server/services/presentations.ts#getPresentationByCode
- kind: doc
  role: intent
  target: docs/requirements/REQ118.md
---

# Join presentation

A participant joins a presentation with its six-digit code, its join link or its QR code.
