---
appliesTo:
- type: entity
  id: slide
  facts:
  - Items
- type: capability
  id: submit-answer
references:
- kind: code
  role: implementation
  target: server/schemas.ts#POINTS_BUDGET
---

# A 100 Points answer spends exactly 100 points

A split of points that does not add up to exactly 100 is refused.
