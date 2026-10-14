---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Workspaces
  kind: actor
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspaces
- text: The page lists each Workspace the Organizer belongs to, with their role in it
  kind: condition
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  - entity: workspace-member
    effect: reads
    facts:
    - Role
  contexts:
    web:
      place: web::signed-in::workspaces
---

# See one's workspaces

## Trigger

The Organizer looks for their team's presentations.

## Outcome

The Organizer opens a Workspace.

## Edge cases

- With no workspace yet, the page explains how to create one or be added to one.
