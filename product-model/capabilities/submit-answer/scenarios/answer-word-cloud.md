---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant types a word or short phrase and chooses Submit
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product adds the Answer to the cloud
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

# Add words to a word cloud

## Trigger

The presenter asks for one word.

## Outcome

The word grows in the cloud as others submit it too.

## Edge cases

- A participant may add words up to the slide's response cap; with a cap of one, a new word replaces the earlier one.
