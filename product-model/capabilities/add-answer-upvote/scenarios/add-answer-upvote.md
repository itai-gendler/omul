---
kind: primary
routes:
  web: Web
steps:
- text: The Participant chooses Upvote on a written Answer
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
- text: The Product adds the Participant's upvote to the Answer
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

# Upvote a written answer

## Trigger

The Participant agrees with what someone wrote.

## Outcome

The Answer rises on the wall.

## Edge cases

- Upvoting stops when the presenter closes the slide.
