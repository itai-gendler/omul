---
kind: validation
routes:
  web: Web
steps:
- text: The Participant tries to send a question while Q&A is off or the presentation has ended
  kind: actor
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product takes nothing
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Q&A enabled
  contexts:
    web:
      place: web::audience::participant-view
---

# Ask while questions are off

## Trigger

The presenter has not opened the floor.

## Outcome

No question is kept.
