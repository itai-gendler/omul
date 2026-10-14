---
kind: edge
routes:
  web: Web
steps:
- text: The Organizer chooses Generate draft deck
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::draft-generator
- text: The language model fails or replies with nothing usable
  kind: condition
  entities: []
  contexts:
    web:
      place: web::studio::draft-generator
- text: The Product creates nothing and says the draft could not be generated
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::draft-generator
---

# The language model fails

## Trigger

The provider is down or returns an unusable draft.

## Outcome

Nothing is created; the Organizer can try again.
