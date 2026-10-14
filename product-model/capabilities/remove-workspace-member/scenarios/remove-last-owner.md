---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses Remove beside the Workspace's only Owner
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-member
    effect: reads
    facts:
    - Name
    - Role
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: 'The Product refuses: the Workspace must keep an owner'
  kind: condition
  entities:
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Remove the last owner

## Trigger

The roster is being cleaned up.

## Outcome

Nobody is removed.
