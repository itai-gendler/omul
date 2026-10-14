---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Reveal results on the current Slide
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
- text: The Product publishes the Slide's tally to the room
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

# Reveal a slide's results

## Trigger

The room has voted and the Organizer wants to discuss the outcome.

## Outcome

Participants see the tally, and it keeps updating.
