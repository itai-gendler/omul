---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Use template on one of the prebuilt decks
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::templates
- text: The Product creates a Presentation in Draft with the template's title and a copy of its slides
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
    - Q&A approval
    - Reactions enabled
    - Chat enabled
    - Ask for names
    - Join bar shown
    - Theme
    - Own theme
    - Logo
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
      place: web::studio::templates
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

# Start from a prebuilt deck

## Trigger

The Organizer would rather adapt a proven format than start from nothing.

## Outcome

An editable draft with the template's slides is open in the editor; the template itself is unchanged.
