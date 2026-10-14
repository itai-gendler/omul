---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer enters an email address and a password that do not match
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product refuses to sign the Organizer in and says the email or password is wrong
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
---

# Wrong email address or password

## Trigger

The Organizer mistypes their password.

## Outcome

The Organizer stays signed out and can try again or reset their password.
