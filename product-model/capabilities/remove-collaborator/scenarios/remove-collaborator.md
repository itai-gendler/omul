---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Remove this person's access beside one person in Share this deck
  kind: actor
  actor: organizer
  entities:
  - entity: collaborator
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::studio::home
- text: The Product removes the share
  kind: product
  actor: organizer
  entities:
  - entity: collaborator
    effect: removes
  contexts:
    web:
      place: web::studio::home
---

# Remove a person's access

## Trigger

A colleague left the project.

## Outcome

That person's next request on the presentation is refused, and it leaves their Shared with You.
