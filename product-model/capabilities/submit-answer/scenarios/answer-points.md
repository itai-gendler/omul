---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant spreads exactly 100 points across the items and chooses Submit points
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
- text: The Product records the split as the Answer
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

# Split 100 points

## Trigger

The presenter asks the room to divide a budget.

## Outcome

The room's total per item includes the Participant's points.

## Edge cases

- Submit points stays unavailable until all 100 points are spent.
