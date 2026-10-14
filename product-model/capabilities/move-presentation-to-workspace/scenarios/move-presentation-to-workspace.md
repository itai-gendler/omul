---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Move to a workspace on a presentation and picks one of their workspaces
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  - entity: workspace
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::studio::home
- text: The Product hands the Presentation to the Workspace, clearing its owner and retiring its edit link
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Workspace
    - Owner
    - Edit link
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::home
- text: The Product opens the Workspace
  kind: condition
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
---

# Move a presentation into a workspace

## Trigger

The Organizer's team takes over a presentation they built alone.

## Outcome

The workspace owns the presentation; its members run it together, and an edit link handed out before no longer works.

## Edge cases

- Accounts the presentation was shared with keep their access.
- When the Organizer is in no workspace that takes new presentations, the dialog says so.
