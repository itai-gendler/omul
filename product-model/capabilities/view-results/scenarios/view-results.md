---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer looks at the tally under the current Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
    - Result display
  contexts:
    web:
      place: web::studio::presenter-view
- text: The tally updates as each Answer arrives, drawn the way the Slide asks for
  kind: condition
  actor: organizer
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
    - Upvoters
  - entity: slide
    effect: reads
    facts:
    - Result display
  contexts:
    web:
      place: web::studio::presenter-view
---

# Follow a slide's tally

## Trigger

The room is answering.

## Outcome

The Organizer sees the room's answers as they land, including tallies the room cannot see.
