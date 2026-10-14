---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Participant enters the code shown on the shared screen
  kind: actor
  actor: participant
  capability: join-presentation
  entities: []
  contexts:
    web:
      place: web::audience::join
- text: The Product finds the Presentation
  kind: product
  actor: participant
  capability: join-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Join code
  contexts:
    web:
      place: web::audience::join
- text: The Participant view opens where the room is
  kind: condition
  actor: participant
  capability: join-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Current slide
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant picks an option and chooses Submit
  kind: actor
  actor: participant
  capability: submit-answer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Options
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the Answer
  kind: product
  actor: participant
  capability: submit-answer
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

# Join and answer

## Trigger

The presenter puts the join code on screen.

## Outcome

The Participant has answered.
