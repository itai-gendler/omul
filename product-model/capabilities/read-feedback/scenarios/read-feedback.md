---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator opens Feedback about omul
  kind: actor
  actor: administrator
  entities:
  - entity: feedback
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::feedback-inbox
- text: The page shows the channel's rating totals and the fifty newest entries, with more on request
  kind: condition
  actor: administrator
  entities:
  - entity: feedback
    effect: reads
    facts:
    - Rating
    - Comment
    - Surface
    - Language
    - Contact
    - Sent on
  contexts:
    web:
      place: web::administration::feedback-inbox
---

# Read the app-menu feedback

## Trigger

The operator reviews what people think of the instance.

## Outcome

The Administrator has read the newest feedback and can write back to those who asked.
