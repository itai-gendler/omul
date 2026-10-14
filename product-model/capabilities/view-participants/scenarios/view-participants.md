---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Show who took part
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The presenter view lists the names participants gave on this presentation
  kind: condition
  actor: organizer
  entities:
  - entity: participant
    effect: reads
    facts:
    - Name
  - entity: presentation
    effect: reads
    facts:
    - Ask for names
  contexts:
    web:
      place: web::studio::presenter-view
---

# See who took part

## Trigger

The Organizer takes attendance.

## Outcome

The Organizer knows who took part.

## Edge cases

- A presentation that does not ask for names has no list to show.
