---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer changes the type of the selected Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Type
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
- text: The Product saves the Slide as the new type
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: changes
    facts:
    - Type
  contexts:
    web:
      place: web::studio::editor
---

# Change a slide's type

## Trigger

A poll would work better as a word cloud.

## Outcome

The Slide is of the new type.
