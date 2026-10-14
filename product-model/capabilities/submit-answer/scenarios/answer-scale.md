---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant rates each statement between the scale's bounds, skipping those the slide lets them skip
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Items
    - Scale
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records one Answer per statement
  kind: product
  actor: participant
  entities:
  - entity: answer
    effect: creates
    facts:
    - Value
    - Statement
    - Skipped
    - Submitted at
  contexts:
    web:
      place: web::audience::participant-view
---

# Rate statements on a scale

## Trigger

The presenter asks how much the room agrees.

## Outcome

The mean per statement includes the Participant's ratings.
