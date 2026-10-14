---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters a name, an email address and a password of at least eight characters, and confirms
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: The Product creates the Account and signs the Organizer in
  kind: product
  actor: organizer
  entities:
  - entity: account
    effect: creates
    facts:
    - Name
    - Email
    - Password
    - Email verified
  contexts:
    web:
      place: web::studio::home
- text: The Product sends a verification link to the email address
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
- text: Home reminds the Organizer to verify their email address
  kind: condition
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts:
    - Email verified
  contexts:
    web:
      place: web::studio::home
---

# Create an account

## Trigger

The Organizer wants their presentations to follow them across devices, or to share them.

## Outcome

The Organizer has an account and is signed in. A verification link is on its way; nothing waits on following it.

## Edge cases

- A name left empty is taken from the part of the email address before the @.
- An email address that already has an account is refused.
- Presentations this browser holds the edit link of become the new account's, as on signing in.
