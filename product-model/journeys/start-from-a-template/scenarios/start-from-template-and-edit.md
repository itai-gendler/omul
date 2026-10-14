---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer chooses Use template on a prebuilt deck
  kind: actor
  actor: organizer
  capability: use-template
  entities: []
  contexts:
    web:
      place: web::studio::templates
- text: The Product creates the Presentation
  kind: product
  actor: organizer
  capability: use-template
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
  capability: use-template
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::editor
- text: The Organizer changes a Slide and chooses Save Changes
  kind: actor
  actor: organizer
  capability: edit-slide
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::studio::editor
- text: The Product saves the Slide
  kind: product
  actor: organizer
  capability: edit-slide
  entities:
  - entity: slide
    effect: changes
    facts:
    - Question
    - Options
  contexts:
    web:
      place: web::studio::editor
---

# Start from a template

## Trigger

The Organizer picks a format from the catalog.

## Outcome

The template's slides are adapted and saved.
