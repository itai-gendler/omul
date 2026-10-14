---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Delete this answer on one word or written Answer
  kind: actor
  actor: organizer
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product deletes the Answer with its upvotes
  kind: product
  actor: organizer
  entities:
  - entity: answer
    effect: removes
  contexts:
    web:
      place: web::studio::presenter-view
---

# Delete a submitted answer

## Trigger

Someone wrote something that must not stay on the wall.

## Outcome

The Answer is gone from the tally on every screen and from every export.
