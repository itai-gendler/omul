---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer picks another role for a Workspace member
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-member
    effect: reads
    facts:
    - Name
    - Role
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product changes the role
  kind: product
  actor: organizer
  entities:
  - entity: workspace-member
    effect: changes
    facts:
    - Role
  contexts:
    web:
      place: web::signed-in::workspace
---

# Change a member's role

## Trigger

A member takes over running the team's presentations.

## Outcome

The new role applies from that member's next request.
