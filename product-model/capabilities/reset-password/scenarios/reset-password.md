---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Forgot password? and enters their email address
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product sends a password reset link to that address
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  contexts:
    web:
      place: web::studio::home
- text: The Organizer follows the link and enters a new password
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product sets the new password
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: changes
    facts:
    - Password
  contexts:
    web:
      place: web::studio::home
---

# Reset a forgotten password

## Trigger

The Organizer cannot remember their password.

## Outcome

The Organizer signs in with the new password.

## Edge cases

- A reset link older than one hour is refused, and a new one can be requested.
