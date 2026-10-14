---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Put this question back in the queue
  kind: actor
  actor: organizer
  entities:
  - entity: audience-question
    effect: reads
    facts:
    - Text
    - Answered at
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product reopens the Audience question
  kind: product
  actor: organizer
  entities:
  - entity: audience-question
    effect: changes
    from: Answered
    to: Open
    facts:
    - Answered at
  contexts:
    web:
      place: web::studio::presenter-view
---

# Put a question back in the queue

## Trigger

The question was marked answered by mistake.

## Outcome

The question is open again.
