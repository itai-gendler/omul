---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Publish as template on one of the Workspace's presentations, names it, describes it and picks a category
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product publishes a Workspace template with a copy of the presentation's slides
  kind: product
  actor: organizer
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
  - entity: slide
    effect: reads
    facts: []
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Publish a template

## Trigger

The team settled on a format it wants everyone to reuse.

## Outcome

Every member sees the template in the Workspace and can start a presentation from it.
