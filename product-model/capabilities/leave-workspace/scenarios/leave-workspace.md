---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Leave beside their own membership and confirms
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-member
    effect: reads
    facts:
    - Role
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product removes the Organizer's membership of the Workspace
  kind: product
  actor: organizer
  entities:
  - entity: workspace-member
    effect: removes
  - entity: workspace
    effect: reads
    facts: []
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

# Leave a workspace

## Trigger

The Organizer moves to another team.

## Outcome

The Workspace is gone from the Organizer's list; its presentations stay with it.
