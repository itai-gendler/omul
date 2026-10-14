---
kind: validation
routes:
  web: Web
steps:
- text: The Participant waits on a presenter-paced Presentation that is still a draft
  kind: actor
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Pace
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant view shows Waiting for presenter... and takes nothing yet
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Pace
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer a presenter-paced presentation that is not live

## Trigger

The Participant joined early.

## Outcome

The Participant answers once the presenter starts.
