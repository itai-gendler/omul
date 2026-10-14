---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer opens Export this session and picks PDF with results
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product downloads the deck rendered slide by slide with each tally underneath
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Type
    - Question
    - Options
    - Content
  - entity: answer
    effect: reads
    facts:
    - Value
  contexts:
    web:
      place: web::studio::presenter-view
---

# Export a PDF with results

## Trigger

The Organizer hands the results round.

## Outcome

The Organizer has a PDF of the deck and its results.
