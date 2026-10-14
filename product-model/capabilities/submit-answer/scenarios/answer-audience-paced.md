---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant moves through an audience-paced Presentation's slides themselves and responds to each
  kind: actor
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Pace
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records each Answer, before the session goes live as well as during
  kind: product
  actor: participant
  entities:
  - entity: answer
    effect: creates
    facts:
    - Value
    - Submitted at
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer at one's own pace

## Trigger

The organizer sends a survey the room completes in its own time.

## Outcome

The Participant has answered every Slide they wanted to, until the presentation ends.

## Edge cases

- Results that need every question answered first say Answer all questions to see results.
