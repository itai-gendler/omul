---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant opens the join link or scans the QR code
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant view opens where the room is
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Current slide
  contexts:
    web:
      place: web::audience::participant-view
---

# Join with the link or the QR code

## Trigger

The presenter reads out the link or shows the QR code.

## Outcome

The Participant is in the room without typing the code.
