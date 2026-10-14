---
kind: validation
routes:
  web: Web
steps:
- text: The Participant submits after the question's time and its short grace have run out
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Time limit
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product takes nothing and says the time for this question is over
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Slide opened at
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer a quiz question too late

## Trigger

The Participant hesitated too long.

## Outcome

No Answer is recorded and the question scores nothing for the Participant.
