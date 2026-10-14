---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant puts the items in their order and chooses Submit
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Items
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the order as the Answer
  kind: product
  actor: participant
  entities:
  - entity: answer
    effect: creates
    facts:
    - Value
    - Submitted at
  contexts:
    web:
      place: web::audience::participant-view
---

# Rank items

## Trigger

The presenter asks the room to prioritize.

## Outcome

The room's ranking includes the Participant's order.
