---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Hide the join bar
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product takes the join bar off the shared screen
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Join bar shown
  contexts:
    web:
      place: web::studio::presenter-view
---

# Hide the join bar

## Trigger

Everyone has joined and the slide needs the room.

## Outcome

The join code stays valid and the room can still join.
