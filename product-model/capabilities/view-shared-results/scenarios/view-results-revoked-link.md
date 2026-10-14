---
kind: edge
routes:
  web: Web
steps:
- text: The Results viewer opens a results link that was revoked or replaced
  kind: actor
  actor: results-viewer
  entities: []
  contexts:
    web:
      place: web::shared-results::results
- text: The page says the results link is no longer valid
  kind: condition
  actor: results-viewer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Results link
  contexts:
    web:
      place: web::shared-results::results
---

# Open a revoked link

## Trigger

The organizer revoked the link.

## Outcome

The Results viewer knows to ask for a new link.
