---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer writes in the chat from the audience panel
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product adds the Chat message for everyone on the presentation
  kind: product
  actor: organizer
  entities:
  - entity: chat-message
    effect: creates
    facts:
    - Text
    - Sent at
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Write in the chat from the presenter view

## Trigger

The presenter answers in the chat.

## Outcome

The room reads it like any other line of the chat.
