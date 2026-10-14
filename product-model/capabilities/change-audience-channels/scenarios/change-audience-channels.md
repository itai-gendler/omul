---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer switches reactions or the chat on or off in the audience panel
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product saves the change and sends it to everyone in the room
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Reactions enabled
    - Chat enabled
  contexts:
    web:
      place: web::studio::presenter-view
---

# Open or close reactions and chat

## Trigger

The Organizer wants a livelier room, or a quieter one.

## Outcome

Participants can react or chat, or not, at once; what was already said stays readable.
