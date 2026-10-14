---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters a new name for the Workspace
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
- text: The Product renames the Workspace
  kind: product
  actor: organizer
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
---

# Rename a workspace

## Trigger

The team was renamed.

## Outcome

Every member sees the new name.
