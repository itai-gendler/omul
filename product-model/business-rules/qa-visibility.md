---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Q&A visibility
- type: capability
  id: send-audience-question
- type: capability
  id: add-audience-question-upvote
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#getQAList
- kind: doc
  role: intent
  target: docs/requirements/REQ037.md
---

# Only the presenter's side reads the room's questions unless they are set for everyone

With Only the presenter, each participant reads only their own questions and nobody upvotes; with Everyone, the room reads the list, most upvoted first, and upvotes others' questions.
