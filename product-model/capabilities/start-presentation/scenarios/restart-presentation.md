---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Restart on an ended presentation
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
- text: The Product takes the Presentation live again from the start
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    from: Ended
    to: Live
    facts:
    - Current slide
    - Session started at
    - Session ended at
  contexts:
    web:
      place: web::studio::presenter-view
---

# Run an ended presentation again

## Trigger

The session continues after a break.

## Outcome

The presentation is live again; what the room submitted so far is kept.
