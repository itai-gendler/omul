---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses New deck in the Workspace
  kind: actor
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product creates an untitled Presentation the Workspace owns, in Draft, with one text slide, in the Workspace's default theme and with no edit link
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
    - Theme
    - Workspace
    - Created at
  - entity: slide
    effect: creates
    facts:
    - Type
    - Question
    - Position
    with: presentation
  - entity: workspace
    effect: reads
    facts:
    - Default theme
  contexts:
    web:
      place: web::signed-in::workspace
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

# Create a presentation in a workspace

## Trigger

The team needs a new presentation.

## Outcome

Every member of the Workspace can edit and run the new presentation.
