---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Delete this comment on a comment they wrote
  kind: actor
  actor: organizer
  entities:
  - entity: slide-comment
    effect: reads
    facts:
    - Body
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product deletes the Slide comment
  kind: product
  actor: organizer
  entities:
  - entity: slide-comment
    effect: removes
  contexts:
    web:
      place: web::studio::presenter-view
---

# Delete one's own comment

## Trigger

The suggestion has been taken care of.

## Outcome

The comment is gone for everyone.
