---
kind: primary
routes:
  web: Web
steps:
- text: The Participant picks an option and chooses Submit
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
    - Options
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the Answer
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
- text: The Participant sees Vote submitted! and, when the reveal mode allows, the live tally
  kind: condition
  actor: participant
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
  - entity: presentation
    effect: reads
    facts:
    - Results visibility
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer a multiple choice slide

## Trigger

The presenter shows a poll.

## Outcome

The Participant's choice counts in the tally.

## Edge cases

- Picking again on a single-choice slide replaces the earlier choice.
- On a slide that allows several choices, each pick counts up to the slide's selection limit.
