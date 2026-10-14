---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant enters a whole number inside the allowed range and on its steps and chooses Submit guess
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Guess range
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the guess as the Answer
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

# Guess the number

## Trigger

The presenter asks the room to estimate.

## Outcome

The distribution of guesses includes the Participant's, against the reference value once shown.

## Edge cases

- A number outside the range, or between two steps, is refused before it is sent.
