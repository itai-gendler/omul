---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer removes the selected Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
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
- text: The Product deletes the Slide
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: removes
  contexts:
    web:
      place: web::studio::editor
---

# Delete a slide

## Trigger

A question is no longer needed.

## Outcome

The presentation no longer has that Slide.
