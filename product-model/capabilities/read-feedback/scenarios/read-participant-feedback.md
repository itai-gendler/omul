---
kind: alternative
routes:
  web: Web
steps:
- text: The Administrator switches Feedback about omul to the after-session channel
  kind: actor
  actor: administrator
  entities:
  - entity: feedback
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::feedback-inbox
- text: The page shows those rating totals and the fifty newest anonymous entries
  kind: condition
  actor: administrator
  entities:
  - entity: participant-feedback
    effect: reads
    facts:
    - Rating
    - Comment
    - Language
    - Sent on
  contexts:
    web:
      place: web::administration::feedback-inbox
---

# Read the after-session answers

## Trigger

The operator checks how participants rated sessions.

## Outcome

The Administrator has read the participants' answers.

## Edge cases

- While both channels are off, the page says so.
