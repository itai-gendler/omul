---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Close submissions on the current Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product closes the Slide; every Answer already given is kept
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Closed slides
  - entity: slide
    effect: reads
    facts: []
  - entity: answer
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Close a slide to submissions

## Trigger

Time is up for a question.

## Outcome

Participants are told the presenter has closed this question.
