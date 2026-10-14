---
kind: edge
routes:
  web: Web
steps:
- text: The Results viewer segments a word cloud, open text, grid, guess or pin slide without being able to edit the presentation
  kind: actor
  actor: results-viewer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::shared-results::results
- text: The breakdown is withheld because what people wrote or placed could identify them
  kind: condition
  entities:
  - entity: slide
    effect: reads
    facts:
    - Type
  contexts:
    web:
      place: web::shared-results::results
---

# Segment a slide whose answers identify people

## Trigger

A reader tries to break down written answers by team.

## Outcome

Nothing is published beyond the unsegmented tally.
