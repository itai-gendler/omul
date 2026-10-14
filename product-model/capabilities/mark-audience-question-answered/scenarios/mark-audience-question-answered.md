---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Mark this question answered
  kind: actor
  actor: organizer
  entities:
  - entity: audience-question
    effect: reads
    facts:
    - Text
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product marks the Audience question answered
  kind: product
  actor: organizer
  entities:
  - entity: audience-question
    effect: changes
    from: Open
    to: Answered
    facts:
    - Answered at
  contexts:
    web:
      place: web::studio::presenter-view
---

# Mark a question answered

## Trigger

The presenter has just answered it out loud.

## Outcome

The question shows as answered and drops below the open ones.
