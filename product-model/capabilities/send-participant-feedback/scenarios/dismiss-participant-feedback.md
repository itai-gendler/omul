---
kind: alternative
routes:
  web: Web
steps:
- text: The prompt asks the Participant what they think of omul
  kind: condition
  actor: participant
  entities:
  - entity: deployment-settings
    effect: reads
    facts:
    - Prompt share
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant chooses Close without answering
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: Nothing is stored and the device is not asked again before the cooldown ends
  kind: condition
  entities:
  - entity: deployment-settings
    effect: reads
    facts:
    - Prompt cooldown
  contexts:
    web:
      place: web::audience::participant-view
---

# Close the prompt without answering

## Trigger

The Participant does not want to answer.

## Outcome

Nothing is kept.
