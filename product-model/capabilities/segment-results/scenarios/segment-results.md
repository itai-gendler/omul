---
kind: primary
routes:
  web: Web
steps:
- text: The Results viewer picks an earlier single-choice Slide to segment a tally by
  kind: actor
  actor: results-viewer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::shared-results::results
- text: The Product splits the tally into one group per option chosen on the earlier Slide
  kind: product
  actor: results-viewer
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
  - entity: slide
    effect: reads
    facts:
    - Options
  contexts:
    web:
      place: web::shared-results::results
- text: Groups of fewer than five people are held back, together with at least one other group, and show no head count
  kind: condition
  entities: []
  contexts:
    web:
      place: web::shared-results::results
---

# Split a tally by an earlier choice

## Trigger

A reader wants to compare how teams answered.

## Outcome

The Results viewer sees the tally per group, with small groups protected.
