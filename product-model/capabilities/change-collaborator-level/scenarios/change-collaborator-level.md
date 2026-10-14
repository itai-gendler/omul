---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer picks another level beside one person in Share this deck
  kind: actor
  actor: organizer
  entities:
  - entity: collaborator
    effect: reads
    facts:
    - Email
    - Level
  contexts:
    web:
      place: web::studio::home
- text: The Product changes the level
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

# Change a level

## Trigger

A reviewer becomes a co-presenter.

## Outcome

The new level applies from that person's next request.
