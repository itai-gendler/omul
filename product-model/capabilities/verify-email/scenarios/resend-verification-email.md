---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Resend email on the reminder on Home
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product sends a new verification link to the email address
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
---

# Resend the verification email

## Trigger

The first verification email never arrived.

## Outcome

A new verification link is on its way.
