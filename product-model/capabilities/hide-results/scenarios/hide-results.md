---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Hide results on a revealed Slide
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
- text: The Product withdraws the Slide's tally from the room
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Revealed slides
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Hide a slide's results again

## Trigger

The Organizer revealed too early.

## Outcome

Participants see that the results are hidden; the answers are kept.
