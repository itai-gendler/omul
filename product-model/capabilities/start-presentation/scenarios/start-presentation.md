---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Start Presentation
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product takes the Presentation live on its first slide and starts that Slide's clock
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    from: Draft
    to: Live
    facts:
    - Current slide
    - Slide opened at
    - Session started at
    - Session ended at
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Start a presentation

## Trigger

The room has gathered.

## Outcome

The presentation is live; everyone who joined sees its first slide.
