---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer chooses Import and picks a .omul.json file
  kind: actor
  actor: organizer
  capability: import-presentation
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product creates the Presentation
  kind: product
  actor: organizer
  capability: import-presentation
  entities:
  - entity: presentation
    effect: creates
    to: Draft
    facts:
    - Title
    - Join code
    - Pace
    - Language
    - Edit link
    - Created at
  - entity: slide
    effect: creates
    facts:
    - Type
    - Question
    - Options
    - Correct answers
    - Content
    - Position
    with: presentation
  contexts:
    web:
      place: web::studio::home
- text: The Product opens the new Presentation in the editor
  kind: condition
  actor: organizer
  capability: import-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::editor
- text: The Organizer changes the title or settings and chooses Save Changes
  kind: actor
  actor: organizer
  capability: edit-presentation
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Product saves the Presentation's settings
  kind: product
  actor: organizer
  capability: edit-presentation
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Title
    - Pace
  contexts:
    web:
      place: web::studio::editor
---

# Import a presentation

## Trigger

The Organizer brings a presentation from another instance.

## Outcome

The imported presentation is adjusted and saved.
