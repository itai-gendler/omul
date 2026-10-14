---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer marks which options of a quiz Slide are correct, or lists the typed replies it accepts
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Options
    - Quiz answer mode
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
- text: The Product saves the correct options
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: changes
    facts:
    - Correct answers
  contexts:
    web:
      place: web::studio::editor
---

# Mark the correct answers of a quiz question

## Trigger

A drafted quiz has no correct answers yet.

## Outcome

The quiz Slide scores participants against its answer key.
