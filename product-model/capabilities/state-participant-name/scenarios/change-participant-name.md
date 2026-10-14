---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant chooses Change beside Joined as and enters another name
  kind: actor
  actor: participant
  entities:
  - entity: participant
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product keeps the new name
  kind: product
  actor: participant
  entities:
  - entity: participant
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::audience::participant-view
---

# Change one's name

## Trigger

The Participant mistyped their name.

## Outcome

The presenter's side shows the corrected name.

## Edge cases

- A name cannot be given once the presentation has ended.
