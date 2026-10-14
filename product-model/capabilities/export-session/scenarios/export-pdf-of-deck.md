---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer opens Export this session and picks PDF of the deck
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product downloads the deck's questions, options and correct options, without anything the room submitted
  kind: product
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Type
    - Question
    - Options
    - Correct answers
    - Content
  contexts:
    web:
      place: web::studio::presenter-view
---

# Export a PDF of the deck

## Trigger

The Organizer shares the questions without the room's answers.

## Outcome

The Organizer has a PDF of the deck alone.
