---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Export on one of their presentations
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::home
- text: The Product downloads a .omul.json file with the presentation's title, settings and slides
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Pace
    - Language
    - Results visibility
    - Q&A enabled
    - Q&A visibility
    - Reactions enabled
    - Chat enabled
  - entity: slide
    effect: reads
    facts:
    - Type
    - Question
    - Options
    - Correct answers
    - Content
    - Position
  contexts:
    web:
      place: web::studio::home
---

# Export a presentation file

## Trigger

The Organizer wants a copy of a presentation outside omul.

## Outcome

The Organizer has a file that holds the presentation without anything the room submitted.
