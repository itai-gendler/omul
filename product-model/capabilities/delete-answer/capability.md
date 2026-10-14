---
availability:
- place: web::studio
domain: presenting
references:
- kind: code
  role: implementation
  target: src/components/Results.tsx#RemoveAnswerButton
- kind: code
  role: implementation
  target: server/services/presentations.ts#deleteSubmittedAnswer
- kind: doc
  role: intent
  target: docs/requirements/REQ027.md
---

# Delete answer

An organizer removes one word or written answer from a Word Cloud or Open Text slide.
