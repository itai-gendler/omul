---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant types a question and chooses Send
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product keeps the Audience question for the presenter's approval
  kind: product
  actor: participant
  entities:
  - entity: audience-question
    effect: creates
    to: Awaiting approval
    facts:
    - Text
    - Asked at
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant is told the question went to the presenter
  kind: condition
  actor: participant
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Q&A approval
  contexts:
    web:
      place: web::audience::participant-view
---

# Ask a question that waits for approval

## Trigger

The presentation moderates its questions.

## Outcome

Only the presenter's side sees the question until it is approved.
