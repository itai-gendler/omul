---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters their email address and password and chooses Sign in
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product checks them and signs the Organizer in
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
    - Password
  contexts:
    web:
      place: web::studio::home
- text: The Product makes the Organizer the owner of every ownerless presentation whose edit link this browser holds
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Owner
  contexts:
    web:
      place: web::studio::home
- text: Home lists the presentations the Organizer owns or holds the edit link of
  kind: condition
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Join code
    - Created at
  contexts:
    web:
      place: web::studio::home
---

# Sign in and keep this browser's presentations

## Trigger

The Organizer returns to omul, on this device or another.

## Outcome

The Organizer is signed in. Presentations they made in this browser before signing in now belong to their account and follow them to other devices.

## Edge cases

- A presentation another account already owns, or a workspace owns, is left as it is.
