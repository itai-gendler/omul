---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer names a new key in Account settings and chooses Create
  kind: actor
  actor: organizer
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::account-settings
- text: The Product creates the API key and shows its value once
  kind: product
  actor: organizer
  entities:
  - entity: api-key
    effect: creates
    facts:
    - Name
    - Key
    - Created at
  contexts:
    web:
      place: web::signed-in::account-settings
---

# Create a key

## Trigger

The Organizer wants to drive omul from a terminal or a script.

## Outcome

The Organizer has copied the key's value; omul never shows it again.
