---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Import and picks a .omul.json file
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product creates a new Presentation in Draft from the file's title, settings and slides, giving every slide a new identity
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: creates
    to: Draft
    facts:
    - Title
    - Join code
    - Pace
    - Language
    - Results visibility
    - Q&A enabled
    - Q&A visibility
    - Reactions enabled
    - Chat enabled
    - Edit link
    - Owner
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
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::editor
---

# Import an exported presentation

## Trigger

The Organizer moves a presentation from another omul instance.

## Outcome

An independent copy of the exported presentation is open in the editor.

## Edge cases

- Q&A visible to everyone, reactions and the chat are switched on only when the file says so explicitly.
