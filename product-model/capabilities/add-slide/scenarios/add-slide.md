---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer picks a type — a question, a leaderboard or content — writes it and chooses Save Changes
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Product adds the new Slide at its position in the Presentation
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: creates
    facts:
    - Type
    - Question
    - Options
    - Correct answers
    - Content
    - Position
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::editor
---

# Add a slide

## Trigger

The Organizer needs one more question.

## Outcome

The new Slide is part of the presentation.

## Edge cases

- A presentation holds at most 200 slides.
