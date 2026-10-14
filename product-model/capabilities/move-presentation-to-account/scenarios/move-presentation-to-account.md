---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses to move one of the Workspace's presentations out to themselves, and confirms
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product moves the Presentation out of the Workspace and makes the Organizer its owner
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Workspace
    - Owner
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Move a presentation to one's own account

## Trigger

A presentation belongs to one person again.

## Outcome

The presentation leaves the Workspace's list and the other members lose access; its old edit link stays retired.
