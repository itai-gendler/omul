---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer enters an email address nobody has signed up with
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product says no account is registered with that email; nothing is shared and no invitation is sent
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::studio::home
---

# Share with an address nobody signed up with

## Trigger

The colleague has not created an account yet.

## Outcome

Nothing is shared.
