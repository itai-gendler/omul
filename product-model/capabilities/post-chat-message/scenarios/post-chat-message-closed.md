---
kind: validation
routes:
  web: Web
steps:
- text: The Participant opens the chat while it is closed
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The chat says it is closed; what was said stays readable
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Chat enabled
  contexts:
    web:
      place: web::audience::participant-view
---

# Write while the chat is closed

## Trigger

The presenter closed the chat.

## Outcome

Nothing new is posted.
