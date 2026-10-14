---
appliesTo:
- type: entity
  id: slide
  facts:
  - Response cap
- type: capability
  id: submit-answer
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitVote
- kind: doc
  role: intent
  target: docs/requirements/REQ022.md
---

# A participant gives at most the slide's response cap on a word cloud or open text slide

Once a participant has given as many answers as the slide allows, more are refused; with a cap of one, a new answer replaces the earlier one. The cap holds even when submissions arrive at once.
