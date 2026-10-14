---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer enters a wrong password and chooses Delete my account permanently
  kind: actor
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::account-settings
- text: The Product refuses and keeps the Account
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts:
    - Password
  contexts:
    web:
      place: web::signed-in::account-settings
---

# Wrong password

## Trigger

The Organizer mistypes their password.

## Outcome

Nothing is deleted.
