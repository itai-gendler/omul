---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant writes a reply and chooses Submit
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product adds the Answer to the wall of written answers
  kind: product
  actor: participant
  entities:
  - entity: answer
    effect: creates
    facts:
    - Value
    - Submitted at
  contexts:
    web:
      place: web::audience::participant-view
---

# Write an open answer

## Trigger

The presenter asks an open question.

## Outcome

The written Answer is on the wall.
