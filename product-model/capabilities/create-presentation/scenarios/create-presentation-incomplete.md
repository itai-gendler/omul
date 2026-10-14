---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses Create before giving a title or writing anything
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The editor says a presentation needs a title and at least one Slide; nothing is created
  kind: condition
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::editor
---

# Create without a title or a slide

## Trigger

The Organizer presses Create too early.

## Outcome

Nothing is created and the editor keeps what was written.
