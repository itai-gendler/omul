---
appliesTo:
- type: entity
  id: audience-question
- type: capability
  id: send-audience-question
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#submitQuestion
---

# A question already asked becomes an upvote

Where the room reads the questions, a question matching one already asked, ignoring case and spacing, counts as an upvote on it; asking one's own question again adds nothing.
