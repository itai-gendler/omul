---
appliesTo:
- type: entity
  id: slide
- type: capability
  id: add-slide
- type: capability
  id: create-presentation
references:
- kind: code
  role: implementation
  target: server/schemas.ts#SLIDE_LIMIT
---

# A presentation holds at most 200 slides

Creating or saving a presentation with more than 200 slides is refused.
