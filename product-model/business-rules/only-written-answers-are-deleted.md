---
appliesTo:
- type: entity
  id: answer
- type: capability
  id: delete-answer
references:
- kind: code
  role: implementation
  target: server/schemas.ts#slideAnswersAreDeletable
---

# Only answers on Word Cloud and Open Text slides can be deleted

Words and written answers can be taken off the wall; choices, ratings, placements and scored quiz answers cannot.
