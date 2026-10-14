---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer switches Questions from the audience on or off, picks Only the presenter or Everyone, or switches Approve questions first
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product saves the settings and sends them to everyone in the room
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Q&A enabled
    - Q&A visibility
    - Q&A approval
  contexts:
    web:
      place: web::studio::presenter-view
---

# Change the Q&A settings

## Trigger

The Organizer opens the floor for questions.

## Outcome

Participants can ask, and read the list or not, as set.
