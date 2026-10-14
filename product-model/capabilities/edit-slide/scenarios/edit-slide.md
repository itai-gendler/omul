---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer selects a Slide and changes its question, options or settings
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Type
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
- text: The Product saves the Slide
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: changes
    facts:
    - Question
    - Options
    - Correct answers
    - Content
    - Selection limit
    - Response cap
    - Answer upvoting
    - Items
    - Scale
    - Skipping allowed
    - Grid axes
    - Guess range
    - Target area
    - Form fields
    - Quiz answer mode
    - Time limit
    - Leaderboard size
    - Result display
    - Results visibility
    - Appearance
    - Presenter notes
  contexts:
    web:
      place: web::studio::editor
---

# Change a slide

## Trigger

The Organizer tunes a question before the session.

## Outcome

The Slide reads as the Organizer wants it.
