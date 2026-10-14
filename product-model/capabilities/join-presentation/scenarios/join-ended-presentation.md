---
kind: edge
routes:
  web: Web
steps:
- text: The Participant opens the join link after the end
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant view says the presentation ended and thanks them for participating
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

# Join a presentation that has ended

## Trigger

The Participant arrives too late.

## Outcome

Nothing more can be submitted.
