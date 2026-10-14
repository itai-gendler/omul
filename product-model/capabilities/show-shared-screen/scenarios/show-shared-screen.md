---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Show the slide again
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product lifts the curtain
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Screen blanked
  contexts:
    web:
      place: web::studio::presenter-view
---

# Show the slide again

## Trigger

The Organizer is ready to continue.

## Outcome

The shared screen shows the current slide again.
