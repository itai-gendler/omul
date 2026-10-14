---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer describes the session and chooses Generate draft deck
  kind: actor
  actor: organizer
  capability: generate-draft-presentation
  entities: []
  contexts:
    web:
      place: web::studio::draft-generator
- text: The Product creates the Presentation
  kind: product
  actor: organizer
  capability: generate-draft-presentation
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
    - Position
    with: presentation
  contexts:
    web:
      place: web::studio::draft-generator
- text: The Product opens the new Presentation in the editor
  kind: condition
  actor: organizer
  capability: generate-draft-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::editor
- text: The Organizer marks the correct options of a quiz Slide and chooses Save Changes
  kind: actor
  actor: organizer
  capability: edit-slide
  entities:
  - entity: slide
    effect: reads
    facts:
    - Options
  contexts:
    web:
      place: web::studio::editor
- text: The Product saves the correct options
  kind: product
  actor: organizer
  capability: edit-slide
  entities:
  - entity: slide
    effect: changes
    facts:
    - Correct answers
  contexts:
    web:
      place: web::studio::editor
---

# Draft a presentation from a prompt

## Trigger

The Organizer has a topic and little time.

## Outcome

The drafted quiz scores participants correctly.
