---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer follows the verification link from their email
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product marks the email address verified and signs the Organizer in
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: changes
    facts:
    - Email verified
  contexts:
    web:
      place: web::studio::home
---

# Follow the verification link

## Trigger

The verification email arrives after the Organizer created their account.

## Outcome

The email address is verified and the reminder on Home is gone.

## Edge cases

- A verification link older than one hour is refused.
