---
availability:
- place: web::studio
domain: presenting
references:
- kind: code
  role: implementation
  target: src/components/SlideComments.tsx#SlideCommentsPanel
- kind: code
  role: implementation
  target: server/services/slide-comments.ts#addSlideComment
- kind: doc
  role: intent
  target: docs/requirements/REQ074.md
---

# Add slide comment

An account with comment access writes a comment on one slide of a presentation.
