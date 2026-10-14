---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Templates and searches, or filters by category
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::templates
- text: Templates lists the prebuilt decks that match, each with its title, description and length
  kind: condition
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::templates
---

# Find a template

## Trigger

The Organizer wants a ready-made retrospective, quiz or feedback round.

## Outcome

The Organizer has found a template to start from.
