---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer chooses Delete workspace while the Workspace still owns presentations
  kind: actor
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product refuses and says how many presentations the Workspace still owns, to move or delete first
  kind: condition
  entities:
  - entity: presentation
    effect: reads
    facts: []
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Delete a workspace that still owns presentations

## Trigger

The Organizer forgot the team's presentations.

## Outcome

Nothing is deleted.
