---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Delete on a draft and confirms
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::home
- text: The Product deletes the Presentation with its slides
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: removes
    from: Draft
  - entity: slide
    effect: removes
    with: presentation
  contexts:
    web:
      place: web::studio::home
---

# Delete a draft

## Trigger

The Organizer abandons a draft.

## Outcome

The draft is gone.
