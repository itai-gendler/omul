---
kind: validation
routes:
  web: Web
steps:
- text: The Participant enters a code nothing has
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::join
- text: Join says the presentation was not found
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Join code
  contexts:
    web:
      place: web::audience::join
---

# Join with a code that finds nothing

## Trigger

The Participant mistypes the code.

## Outcome

The Participant can try again.

## Edge cases

- A code that is not six digits is refused before anything is looked up.
