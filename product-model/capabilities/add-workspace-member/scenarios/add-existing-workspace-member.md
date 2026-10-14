---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer adds an address that is already a member, at another role
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-member
    effect: reads
    facts:
    - Email
    - Role
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product changes that membership's role instead of adding another
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

# Add someone who is already a member

## Trigger

The Organizer forgot the colleague was already in.

## Outcome

The colleague has one membership, at the new role.
