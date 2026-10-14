---
kind: validation
routes:
  web: Web
steps:
- text: The Results viewer looks at an entry the picker shows disabled
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
- text: 'The picker says why: a later Slide, a multi-select or typed slide, or one without a fixed set of choices'
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

# Segment by a slide that cannot group

## Trigger

The reader wants to group by a word cloud.

## Outcome

No breakdown is made.
