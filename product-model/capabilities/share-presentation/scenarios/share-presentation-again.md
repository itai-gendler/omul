---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer shares the presentation again with someone who already has access, at another level
  kind: actor
  actor: organizer
  entities:
  - entity: collaborator
    effect: reads
    facts:
    - Email
    - Level
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::home
- text: The Product changes the existing share to the new level instead of adding another
  kind: product
  actor: organizer
  entities:
  - entity: collaborator
    effect: changes
    facts:
    - Level
  contexts:
    web:
      place: web::studio::home
---

# Share again with the same person

## Trigger

The Organizer forgot the colleague already had access.

## Outcome

The colleague has one share, at the new level.
