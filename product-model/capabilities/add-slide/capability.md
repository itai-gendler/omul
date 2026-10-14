---
availability:
- place: web::studio
domain: editor
references:
- kind: code
  role: implementation
  target: src/components/SlideTypeMenu.tsx
- kind: code
  role: implementation
  target: src/store/editor.ts
- kind: code
  role: implementation
  target: server/schemas.ts#SlideTypeEnum
---

# Add slide

An organizer adds a slide of one of the seventeen types to a presentation.
