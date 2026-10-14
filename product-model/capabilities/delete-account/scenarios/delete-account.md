---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters their password and chooses Delete my account permanently
  kind: actor
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::account-settings
- text: The Product deletes the Account and signs the Organizer out
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: removes
  contexts:
    web:
      place: web::signed-in::account-settings
---

# Delete the account

## Trigger

The Organizer no longer wants an account.

## Outcome

The account is gone and the Organizer is signed out.
