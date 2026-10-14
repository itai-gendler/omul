---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant taps the image to place a pin
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Target area
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the pin as the Answer
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

# Pin on an image

## Trigger

The presenter shows a map or a diagram.

## Outcome

The Participant's pin is among the room's and, where the slide has a target area, is shown inside or outside it.
