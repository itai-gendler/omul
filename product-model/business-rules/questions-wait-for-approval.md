---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Q&A approval
- type: capability
  id: send-audience-question
- type: capability
  id: approve-audience-question
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitQuestion
- kind: doc
  role: intent
  target: docs/requirements/REQ038.md
---

# With approval on, a question reaches the room only once approved

While a presentation asks for approval, each new question waits for the presenter's side; only approved questions are listed for the room or upvoted.
