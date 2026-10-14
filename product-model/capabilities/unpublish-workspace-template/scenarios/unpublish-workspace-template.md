---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Unpublish on a Workspace template and confirms
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-template
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product takes the Workspace template down; no presentation changes
  kind: product
  actor: organizer
  entities:
  - entity: workspace-template
    effect: removes
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Unpublish a template

## Trigger

The format is retired.

## Outcome

Members can no longer start from it; presentations made from it are untouched.
