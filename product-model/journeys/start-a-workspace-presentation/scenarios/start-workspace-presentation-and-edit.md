---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer chooses New deck in a Workspace
  kind: actor
  actor: organizer
  capability: create-workspace-presentation
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product creates a Presentation the Workspace owns
  kind: product
  actor: organizer
  capability: create-workspace-presentation
  entities:
  - entity: presentation
    effect: creates
    to: Draft
    facts:
    - Title
    - Join code
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
  capability: create-workspace-presentation
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

# Start a workspace presentation

## Trigger

The team needs a new presentation.

## Outcome

The workspace's presentation is written and every member can run it.
