---
kind: primary
routes:
  web: Web
steps:
- text: The Participant taps Nice, Love it, Celebrate, Funny or Good point
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product shows the reaction crossing the shared screen and keeps nothing
  kind: product
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Reactions enabled
  contexts:
    web:
      place: web::audience::participant-view
---

# React on any slide

## Trigger

Something on the slide lands with the Participant.

## Outcome

The room sees the reaction; nothing is stored.
