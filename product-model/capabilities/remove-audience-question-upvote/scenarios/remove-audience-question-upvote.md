---
kind: primary
routes:
  web: Web
steps:
- text: The Participant chooses the upvote they gave again
  kind: actor
  actor: participant
  entities:
  - entity: audience-question
    effect: reads
    facts:
    - Text
    - Upvoters
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product removes the Participant's upvote from the Audience question
  kind: product
  actor: participant
  entities:
  - entity: audience-question
    effect: changes
    facts:
    - Upvoters
  contexts:
    web:
      place: web::audience::participant-view
---

# Take back an upvote

## Trigger

The Participant upvoted the wrong question.

## Outcome

The question has one upvote fewer.
