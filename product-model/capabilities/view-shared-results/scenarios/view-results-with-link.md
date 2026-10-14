---
kind: primary
routes:
  web: Web
steps:
- text: The Results viewer opens the Presentation's results link
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
- text: The page shows every question Slide's tally, including those the reveal mode keeps from the room
  kind: condition
  actor: results-viewer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
    - Options
  - entity: answer
    effect: reads
    facts:
    - Value
  contexts:
    web:
      place: web::shared-results::results
---

# Open the results link

## Trigger

A stakeholder was sent the results link.

## Outcome

The Results viewer reads the results without an account, and changes nothing.
