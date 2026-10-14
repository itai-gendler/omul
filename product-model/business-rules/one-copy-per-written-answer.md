---
appliesTo:
- type: entity
  id: answer
- type: capability
  id: submit-answer
- type: capability
  id: add-answer-upvote
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitVote
---

# A repeated written answer becomes an upvote where answers can be upvoted

On an Open Text slide that allows upvotes, an answer matching one another participant already gave, ignoring case and spacing, counts as an upvote on that answer instead of a second copy.
