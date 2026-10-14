---
appliesTo:
- type: entity
  id: audience-question
  effect: changes
  facts:
  - Upvoters
permits:
- actors:
  - participant
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#upvoteQuestion
---

# Participants upvote the room's questions

Upvotes on a question are given and taken back by participants, each for themselves.
