---
kind: validation
routes:
  web: Web
steps:
- text: The Participant submits on a Slide the presenter has closed
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
- text: The Product takes nothing and says the presenter has closed this question
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Closed slides
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer a closed slide

## Trigger

The presenter closed submissions.

## Outcome

No Answer is recorded; the ones already given stay.
