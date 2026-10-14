---
appliesTo:
- type: entity
  id: slide
  facts:
  - Guess range
- type: capability
  id: submit-answer
references:
- kind: code
  role: implementation
  target: server/schemas.ts#GuessRangeSchema
---

# A guess must be a whole number inside the range and on its steps

A Guess the Number answer outside the slide's range, or between two of its steps, is refused.
