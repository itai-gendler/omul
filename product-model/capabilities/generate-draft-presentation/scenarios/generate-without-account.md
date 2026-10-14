---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer, not signed in, chooses Generate draft deck
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::draft-generator
- text: Generate a deck says this server only drafts for signed-in organizers; nothing is sent
  kind: condition
  actor: organizer
  entities:
  - entity: deployment-settings
    effect: reads
    facts:
    - Anonymous drafting
  contexts:
    web:
      place: web::studio::draft-generator
---

# Drafting refused without an account

## Trigger

The Organizer tries drafting before creating an account.

## Outcome

Nothing is drafted until the Organizer signs in.
