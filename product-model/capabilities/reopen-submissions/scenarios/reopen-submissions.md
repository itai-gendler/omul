---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Submissions closed — reopen on a closed Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product opens the Slide to submissions again
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Closed slides
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Reopen a closed slide

## Trigger

Latecomers still want to answer.

## Outcome

The room can answer alongside what was already collected.
