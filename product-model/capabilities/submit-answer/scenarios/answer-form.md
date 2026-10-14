---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant fills in the form's fields and chooses Send
  kind: actor
  actor: participant
  entities:
  - entity: slide
    effect: reads
    facts:
    - Form fields
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product records the whole form as one Answer
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

# Fill in a form

## Trigger

The presenter collects sign-ups or details.

## Outcome

Only the organizer's side reads what the Participant wrote.

## Edge cases

- A required field left blank, an email field without an address, or an answer over 200 characters is refused.
- Sending again updates the Participant's answers.
