---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant places each item on the grid, or marks it not assessable where the slide allows
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Items
    - Grid axes
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records one Answer per item
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

# Place items on a 2x2 grid

## Trigger

The presenter asks the room to weigh options on two axes.

## Outcome

The grid shows where the room places each item.
