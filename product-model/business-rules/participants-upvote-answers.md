---
appliesTo:
- type: entity
  id: answer
  effect: changes
  facts:
  - Upvoters
permits:
- actors:
  - participant
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#voteOnResponse
---

# Participants upvote written answers

Upvotes on a written answer are given and taken back by participants, each for themselves.
