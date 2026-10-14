---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer names a new workspace and chooses Create
  kind: actor
  actor: organizer
  capability: create-workspace
  entities:
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspaces
- text: The Product creates the Workspace with the Organizer as Owner
  kind: product
  actor: organizer
  capability: create-workspace
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
  capability: create-workspace
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Organizer adds a colleague by the email address they signed up with
  kind: actor
  actor: organizer
  capability: add-workspace-member
  entities: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product adds the colleague to the Workspace
  kind: product
  actor: organizer
  capability: add-workspace-member
  entities:
  - entity: workspace-member
    effect: creates
    facts:
    - Role
    - Email
    - Name
    - Added at
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Create a workspace and add a colleague

## Trigger

A team starts using omul together.

## Outcome

The team's workspace has its members.
