---
appliesTo:
- type: entity
  id: presentation
- type: capability
  id: delete-presentation
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#deletePresentation
- kind: doc
  role: intent
  target: docs/requirements/REQ146.md
---

# Deleting a presentation erases everything the room left on it

Answers, upvotes, questions, chat, the names participants gave, its shares and its comments go with the presentation.
