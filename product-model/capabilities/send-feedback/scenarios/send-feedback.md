---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens the form in the app menu and gives a rating, a comment or both
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio
- text: The Product stores the Feedback for the people who run the instance, with a way back to the Organizer only when they asked to be contacted
  kind: product
  actor: organizer
  entities:
  - entity: feedback
    effect: creates
    facts:
    - Rating
    - Comment
    - Surface
    - Language
    - Contact
    - Sent on
  contexts:
    web:
      place: web::studio
---

# Send feedback from the app menu

## Trigger

Something about omul helped or got in the way.

## Outcome

The people who run the instance can read it; no organizer or presentation sees it.
