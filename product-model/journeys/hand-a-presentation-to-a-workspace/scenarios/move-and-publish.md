---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer chooses Move to a workspace on a presentation and picks a Workspace
  kind: actor
  actor: organizer
  capability: move-presentation-to-workspace
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::home
- text: The Product hands the Presentation to the Workspace
  kind: product
  actor: organizer
  capability: move-presentation-to-workspace
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Workspace
    - Owner
    - Edit link
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::home
- text: The Product opens the Workspace
  kind: condition
  actor: organizer
  capability: move-presentation-to-workspace
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Organizer chooses Publish as template on that presentation
  kind: actor
  actor: organizer
  capability: publish-workspace-template
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product publishes a Workspace template from it
  kind: product
  actor: organizer
  capability: publish-workspace-template
  entities:
  - entity: workspace-template
    effect: creates
    facts:
    - Title
    - Description
    - Category
    - Tags
    - Slides
    - Published by
    - Published at
  contexts:
    web:
      place: web::signed-in::workspace
---

# Move a presentation in and publish it

## Trigger

A format proved itself.

## Outcome

Every member can start from it.
