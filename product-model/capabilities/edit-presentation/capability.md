---
availability:
- place: web::studio
domain: editor
references:
- kind: code
  role: implementation
  target: src/pages/CreatePage.tsx#CreatePage
- kind: code
  role: implementation
  target: server/services/presentations.ts#updatePresentation
- kind: code
  role: implementation
  target: server/schemas.ts#UpdatePresentationSchema
---

# Edit presentation

An organizer changes a presentation's title and its settings: pace, language, reveal mode, Q&A, audience channels, names, theme and logo.
