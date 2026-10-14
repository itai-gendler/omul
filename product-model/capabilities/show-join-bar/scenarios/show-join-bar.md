---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Show the join bar
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product shows the join code, link and QR code on the shared screen
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

# Show the join bar

## Trigger

Latecomers arrive.

## Outcome

The join bar is back on the shared screen.
