---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer writes a title and the first questions and chooses Create
  kind: actor
  actor: organizer
  capability: create-presentation
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Product creates the Presentation in Draft
  kind: product
  actor: organizer
  capability: create-presentation
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
      place: web::studio::editor
- text: The Product opens its presenter view
  kind: condition
  actor: organizer
  capability: create-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Join code
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Organizer chooses Start Presentation
  kind: actor
  actor: organizer
  capability: start-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product takes the Presentation live
  kind: product
  actor: organizer
  capability: start-presentation
  entities:
  - entity: presentation
    effect: changes
    from: Draft
    to: Live
    facts:
    - Current slide
    - Slide opened at
    - Session started at
    - Session ended at
  contexts:
    web:
      place: web::studio::presenter-view
---

# Create a presentation and start it

## Trigger

The Organizer has a session to run.

## Outcome

The presentation is live.
