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
      place: web::signed-in::workspace
- text: The Product says no account is registered with that email; nobody is added and no invitation is sent
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::signed-in::workspace
---

# Add an address nobody signed up with

## Trigger

The colleague has no account yet.

## Outcome

Nobody is added.
