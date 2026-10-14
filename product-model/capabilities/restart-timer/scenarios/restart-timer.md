---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Restart timer on a quiz Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Time limit
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product restarts the Slide's window from now
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Slide opened at
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Restart a quiz question's timer

## Trigger

The room was not ready when the question opened.

## Outcome

The countdown starts again for everyone; answers already given stay final.
