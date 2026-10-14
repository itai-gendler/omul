---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Share this deck, enters the email address someone signed up with and picks Can view, Can comment or Can edit
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product shares the Presentation with that person at that level
  kind: product
  actor: organizer
  entities:
  - entity: collaborator
    effect: creates
    facts:
    - Level
    - Email
    - Shared at
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::home
---

# Share a presentation

## Trigger

The Organizer wants a colleague to review or co-run a presentation.

## Outcome

The colleague finds the presentation under Shared with You and may do what the level allows.

## Edge cases

- With no level chosen, the share is Can view.
- Sharing with the presentation's own owner is refused.
