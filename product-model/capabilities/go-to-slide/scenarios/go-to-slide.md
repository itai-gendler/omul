---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer moves to the next or the previous Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product shows that Slide to the room and, the first time it is shown, starts its clock
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Current slide
    - Slide opened at
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Move to the next slide

## Trigger

The room has answered the current question.

## Outcome

Every participant's device moves to the same Slide.

## Edge cases

- On an audience-paced presentation each participant moves through the slides themselves.
