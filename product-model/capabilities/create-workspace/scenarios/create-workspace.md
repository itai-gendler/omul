---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer names a new workspace and chooses Create
  kind: actor
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspaces
- text: The Product creates the Workspace with the Organizer as its first Owner
  kind: product
  actor: organizer
  entities:
  - entity: workspace
    effect: creates
    facts:
    - Name
    - Default theme
    - Created at
  - entity: workspace-member
    effect: creates
    facts:
    - Role
    - Email
    - Name
    - Added at
    with: workspace
  contexts:
    web:
      place: web::signed-in::workspaces
- text: The Product opens the new Workspace
  kind: condition
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
---

# Create a workspace

## Trigger

The Organizer's team wants to own its presentations together.

## Outcome

The Workspace exists with the Organizer as its owner.
