---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer gives the new deck a title and writes its first questions and content in the editor
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Organizer chooses Create
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Product creates the Presentation in Draft with its slides, its own six-digit join code and an edit link this browser keeps
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
      place: web::studio::editor
- text: The Product opens the presenter view of the new Presentation
  kind: condition
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Join code
  contexts:
    web:
      place: web::studio::presenter-view
---

# Create a presentation in the browser

## Trigger

The Organizer prepares questions for a meeting, a class or a talk.

## Outcome

The presentation exists as a draft the room can already join with its code, and the Organizer is on its presenter view.

## Decision points

### Is the Organizer signed in?

Whether the new presentation gets an owner.

- Signed in → the Organizer's account owns it, and it follows them to other devices
- Not signed in → it has no owner; the edit link kept in this browser is what lets the Organizer edit and run it

## Edge cases

- A presentation holds at most 200 slides.
