---
kind: primary
routes:
  web: Web
steps:
- text: The Presentation asks everyone joining for their name before they take part
  kind: condition
  actor: participant
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
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product keeps the name for this Presentation and shows it on the presenter's side
  kind: product
  actor: participant
  entities:
  - entity: participant
    effect: changes
    facts:
    - Name
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::audience::participant-view
---

# Give one's name

## Trigger

The organizer needs to know who answered.

## Outcome

The Participant takes part under their name, shown as Joined as.
