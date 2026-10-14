---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters a new email address in Account settings
  kind: actor
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::signed-in::account-settings
- text: The Product sends a confirmation link to the current email address
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::signed-in::account-settings
- text: The Organizer follows the confirmation link
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product sends a verification link to the new email address
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Organizer follows the verification link
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product moves the Account to the new email address
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: changes
    facts:
    - Email
    - Email verified
  contexts:
    web:
      place: web::studio::home
---

# Change the email address

## Trigger

The Organizer changes jobs or mail providers.

## Outcome

The Organizer signs in with the new email address; the old one no longer works.
