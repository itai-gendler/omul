---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer moves a Slide up or down, or drags it to another position
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Position
  contexts:
    web:
      place: web::studio::editor
- text: The Organizer chooses Save Changes
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Product saves the new order
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: changes
    facts:
    - Position
  contexts:
    web:
      place: web::studio::editor
---

# Move a slide

## Trigger

The leaderboard should come after the last quiz question.

## Outcome

The slides run in the new order.
