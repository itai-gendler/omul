---
kind: alternative
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
- text: The Participant view opens and asks for the Participant's name
  kind: condition
  actor: participant
  capability: join-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Ask for names
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant enters their name and chooses Continue
  kind: actor
  actor: participant
  capability: state-participant-name
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product keeps the name
  kind: product
  actor: participant
  capability: state-participant-name
  entities:
  - entity: participant
    effect: changes
    facts:
    - Name
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

# Join, give a name and answer

## Trigger

The presentation asks for names.

## Outcome

The Participant has answered under their name.
