---
kind: primary
routes:
  web: Web
steps:
- text: The Participant chooses Upvote this question on someone else's question
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
- text: The Product adds the Participant's upvote to the Audience question
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

# Upvote a question

## Trigger

The Participant wants the same question answered.

## Outcome

The question moves up the list.

## Edge cases

- Upvoting is offered only when everyone reads the questions.
- A participant's own question already counts as theirs and cannot be upvoted.
