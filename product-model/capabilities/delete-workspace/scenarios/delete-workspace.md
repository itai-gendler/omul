---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Delete workspace and confirms
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
- text: The Product deletes the Workspace with every membership and every template it published
  kind: product
  actor: organizer
  entities:
  - entity: workspace
    effect: removes
  - entity: workspace-member
    effect: removes
    with: workspace
  - entity: workspace-template
    effect: removes
    with: workspace
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product returns to Workspaces
  kind: condition
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspaces
---

# Delete an empty workspace

## Trigger

The team disbanded and moved its presentations out.

## Outcome

The Workspace and its memberships are gone.
