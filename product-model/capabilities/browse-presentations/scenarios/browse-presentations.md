---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Home
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: Home lists, newest first, the presentations this browser holds the edit link of and those the Organizer owns
  kind: condition
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Join code
    - Created at
    - Owner
  contexts:
    web:
      place: web::studio::home
- text: Under Shared with You, Home lists the presentations shared with the Organizer, each with what they may do
  kind: condition
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Join code
  - entity: collaborator
    effect: reads
    facts:
    - Level
  contexts:
    web:
      place: web::studio::home
---

# See one's presentations on Home

## Trigger

The Organizer looks for the presentation they need today.

## Outcome

The Organizer opens the one they want.

## Edge cases

- Shared with You appears only when something is shared with the Organizer.
