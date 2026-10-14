---
kind: primary
routes:
  web: Web
steps:
- text: The Participant chooses Remove upvote on an Answer they upvoted
  kind: actor
  actor: participant
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
    - Upvoters
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product removes the Participant's upvote
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

# Take back an upvote

## Trigger

The Participant upvoted by mistake.

## Outcome

The Answer has one upvote fewer.
