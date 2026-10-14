---
appliesTo:
- type: entity
  id: slide
  facts:
  - Time limit
- type: capability
  id: submit-answer
- type: capability
  id: restart-timer
references:
- kind: code
  role: implementation
  target: server/schemas.ts#QUIZ_SUBMISSION_GRACE_MS
- kind: doc
  role: intent
  target: docs/requirements/REQ057.md
---

# A quiz question takes answers only within its time limit

A quiz question's window opens when its slide is first shown, or when the presenter restarts its timer, and closes when its time limit runs out. An answer arriving within a grace of a second and a half after that is still taken, and scores as one at the buzzer. A question with no time limit, and every quiz question on an audience-paced presentation, is untimed.
