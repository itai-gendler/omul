---
kind: primary
routes:
  web: Web
steps:
- text: The Participant picks an option before the question's time runs out
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
    - Options
    - Time limit
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the Answer as final
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
- text: Once the window closes, the Participant sees whether the Answer was correct, the points it scored and their score so far
  kind: condition
  actor: participant
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
    - Submitted at
  - entity: slide
    effect: reads
    facts:
    - Correct answers
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer a quiz question

## Trigger

The presenter runs a quiz round.

## Outcome

The Participant scored points for a correct Answer, more the faster it came, and climbs the leaderboard.
