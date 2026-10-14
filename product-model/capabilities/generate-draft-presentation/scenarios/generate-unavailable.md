---
kind: edge
routes:
  web: Web
steps:
- text: The Organizer opens Generate a deck on an instance without a language model provider
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::draft-generator
- text: The generate control is disabled and says why
  kind: condition
  entities:
  - entity: deployment-settings
    effect: reads
    facts:
    - Drafting provider
  contexts:
    web:
      place: web::studio::draft-generator
---

# No language model configured

## Trigger

The Organizer looks for drafting on an instance that does not offer it.

## Outcome

The Organizer starts blank or from a template instead.
