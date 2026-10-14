---
domain: audience-channels
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredChatMessageSchema
- kind: code
  role: implementation
  target: server/services/presentations.ts#postChatMessage
---

# Chat message

A line written in a presentation's live chat. Chat messages carry no name.

## Information kept

- **Text** — what was written
- **Sent at** — when it was sent
