---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Republish on a presentation already published as a template
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  - entity: workspace-template
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product replaces the Workspace template's slides with the presentation's current ones
  kind: product
  actor: organizer
  entities:
  - entity: workspace-template
    effect: changes
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

# Republish a template

## Trigger

The source presentation was improved.

## Outcome

Presentations started from the template from now on get the new slides; earlier ones are unchanged.
