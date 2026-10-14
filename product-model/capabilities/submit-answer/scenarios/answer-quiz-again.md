---
kind: validation
routes:
  web: Web
steps:
- text: The Participant tries to change what they already gave on a quiz question
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
- text: The Product keeps the first Answer and says it is final
  kind: condition
  actor: participant
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer a quiz question twice

## Trigger

The Participant changes their mind.

## Outcome

The first Answer stands.
