---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses Save Changes while one Slide lacks what its type needs
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
- text: The editor selects that Slide and says what it lacks; nothing is saved
  kind: condition
  entities:
  - entity: slide
    effect: reads
    facts:
    - Type
  contexts:
    web:
      place: web::studio::editor
---

# A slide is missing what its type needs

## Trigger

A 2x2 Grid slide has an axis without a title.

## Outcome

Nothing is saved until the Slide is complete.
