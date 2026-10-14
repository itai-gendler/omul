---
kind: alternative
routes:
  web: Web
steps:
- text: The Results viewer opens the results page of a Presentation without its link
  kind: actor
  actor: results-viewer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::shared-results::results
- text: Tallies the reveal mode keeps from the room are shown as withheld
  kind: condition
  actor: results-viewer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Results visibility
    - Revealed slides
  - entity: slide
    effect: reads
    facts:
    - Results visibility
  contexts:
    web:
      place: web::shared-results::results
---

# Open the results page without the link

## Trigger

Someone guessed the results address.

## Outcome

The Results viewer sees only what the room could see.
