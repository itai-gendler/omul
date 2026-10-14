---
appliesTo:
- type: entity
  id: slide-comment
  effect: removes
permits:
- related:
  - verb: writes
    entity: organizer
references:
- kind: code
  role: implementation
  target: server/services/slide-comments.ts#deleteSlideComment
---

# Only its author deletes a slide comment

Taking back a comment is part of writing it; nobody else removes it, the presentation's owner included.
