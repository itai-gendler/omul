---
appliesTo:
- type: entity
  id: slide
  facts:
  - Correct answers
- type: capability
  id: submit-answer
- type: capability
  id: join-presentation
references:
- kind: code
  role: implementation
  target: server/schemas.ts#withAudienceSlides
- kind: doc
  role: intent
  target: docs/api.md
  title: The answer key is not shipped to competitors
---

# The room learns a quiz question's answer only after its window closes

The correct answers of a quiz question reach participants once its window has closed or the presentation has ended, never while it can still be answered.
