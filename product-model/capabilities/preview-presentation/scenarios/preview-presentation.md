---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Preview
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::preview
- text: The Product runs the whole Presentation with generated test votes and stores none of them
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Results visibility
  - entity: slide
    effect: reads
    facts:
    - Type
    - Question
    - Options
    - Correct answers
  contexts:
    web:
      place: web::studio::preview
- text: Preview shows each Slide as the presenter's side and the room would see it, including what the reveal mode keeps from the room
  kind: condition
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::studio::preview
---

# Preview a presentation

## Trigger

The Organizer checks a presentation before running it.

## Outcome

The Organizer has seen every Slide with plausible tallies; the presentation has collected nothing.
