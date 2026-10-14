---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses one of the templates the Workspace publishes
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-template
    effect: reads
    facts:
    - Title
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product creates a Presentation the Workspace owns, in Draft, with a copy of the template's slides, in the Workspace's default theme
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
    - Options
    - Correct answers
    - Content
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

# Start from a template the workspace publishes

## Trigger

The team runs its standard retrospective again.

## Outcome

A new presentation of the workspace's is open in the editor, built from the template's slides as they were published.
