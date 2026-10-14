---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer picks another role for the Workspace's only Owner
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
- text: 'The Product refuses: the Workspace must keep an owner'
  kind: condition
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
---

# Demote the last owner

## Trigger

The only owner tries to step down.

## Outcome

The role is unchanged until someone else is made an owner.
