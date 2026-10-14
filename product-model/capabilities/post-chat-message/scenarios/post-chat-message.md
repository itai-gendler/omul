---
kind: primary
routes:
  web: Web
steps:
- text: The Participant writes up to 300 characters in the chat and chooses Send
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product adds the Chat message, without a name, for everyone on the presentation
  kind: product
  actor: participant
  entities:
  - entity: chat-message
    effect: creates
    facts:
    - Text
    - Sent at
  - entity: presentation
    effect: reads
    facts:
    - Chat enabled
  contexts:
    web:
      place: web::audience::participant-view
---

# Write in the chat

## Trigger

A participant wants to say something to the room.

## Outcome

Everyone in the room reads it; the Participant sees it marked as theirs.
