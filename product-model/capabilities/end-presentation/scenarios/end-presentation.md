---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses End
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product ends the session
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    from: Live
    to: Ended
    facts:
    - Session ended at
  contexts:
    web:
      place: web::studio::presenter-view
---

# End a presentation

## Trigger

The talk is over.

## Outcome

Participants see that the presentation ended and take nothing more; tallies the reveal mode withheld stay withheld.
