---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant writes, word for word, what another participant already wrote, on a slide that allows upvotes
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Answer upvoting
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product counts it as the Participant's upvote on the existing Answer
  kind: product
  actor: participant
  entities:
  - entity: answer
    effect: changes
    facts:
    - Upvoters
  contexts:
    web:
      place: web::audience::participant-view
---

# Write an answer someone already wrote

## Trigger

Two people think the same thing.

## Outcome

The wall shows the Answer once, with one more upvote.
