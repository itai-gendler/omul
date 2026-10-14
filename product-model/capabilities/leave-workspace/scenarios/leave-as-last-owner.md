---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer, the Workspace's only Owner, chooses Leave
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-member
    effect: reads
    facts:
    - Role
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product refuses and asks the Organizer to make somebody else an owner first
  kind: condition
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Leave as the last owner

## Trigger

The owner wants out.

## Outcome

The Organizer stays until another owner exists.
