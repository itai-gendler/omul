---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Revoke key beside one of their keys
  kind: actor
  actor: organizer
  entities:
  - entity: api-key
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::account-settings
- text: The Product revokes the API key
  kind: product
  actor: organizer
  entities:
  - entity: api-key
    effect: removes
  contexts:
    web:
      place: web::signed-in::account-settings
---

# Revoke a key

## Trigger

A key was left on a machine the Organizer no longer uses.

## Outcome

Requests made with that key are refused from then on.
