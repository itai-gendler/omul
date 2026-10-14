---
kind: primary
routes:
  web: Web
steps:
- text: The Participant enters the six-digit code shown on the shared screen and chooses Join
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::join
- text: The Product finds the Presentation with that join code
  kind: product
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Join code
  contexts:
    web:
      place: web::audience::join
- text: The Participant view opens, waiting for the presenter while the Presentation is a draft
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::audience::participant-view
---

# Join with the code

## Trigger

The presenter puts the code on screen.

## Outcome

The Participant is in the room, in the presentation's language and theme, and follows it from their device.
