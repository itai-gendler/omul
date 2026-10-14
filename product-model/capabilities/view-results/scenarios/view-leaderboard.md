---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer shows a Leaderboard Slide
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Leaderboard size
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Leaderboard ranks participants by their quiz points across the presentation
  kind: condition
  actor: organizer
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
    - Submitted at
  - entity: participant
    effect: reads
    facts: []
  - entity: slide
    effect: reads
    facts:
    - Leaderboard size
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Show the leaderboard

## Trigger

The quiz round is over.

## Outcome

The room sees the top places, and each participant sees their own position on their device.
