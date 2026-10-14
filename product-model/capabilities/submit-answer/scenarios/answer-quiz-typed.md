---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant types a reply to a quiz question that is answered by typing
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
    - Time limit
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the Answer as final and judges it against the accepted answers, ignoring case, accents, spacing and surrounding punctuation
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

# Type the answer to a quiz question

## Trigger

The quiz asks for a name or a number rather than a choice.

## Outcome

The Answer scores like a picked one when it matches.
