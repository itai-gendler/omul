---
availability:
- place: web::studio
domain: editor
references:
- kind: code
  role: implementation
  target: src/components/SlideEditor.tsx#SlideEditor
- kind: code
  role: implementation
  target: src/pages/CreatePage.tsx#CreatePage
- kind: code
  role: implementation
  target: server/schemas.ts#SlideSchema
---

# Edit slide

An organizer changes a slide: its type, question, options, correct answers, content, settings, appearance and presenter notes.
