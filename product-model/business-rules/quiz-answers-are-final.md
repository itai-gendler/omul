---
appliesTo:
- type: entity
  id: answer
- type: capability
  id: submit-answer
- type: capability
  id: restart-timer
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitVote
- kind: doc
  role: intent
  target: docs/requirements/REQ147.md
---

# A participant's answer to a quiz question is final

The first answer a participant gives to a quiz question stands; a second is refused, even when two arrive at once or the presenter restarts the timer.
