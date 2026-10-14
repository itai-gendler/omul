---
kind: primary
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
- text: The Product adds it to the queue
  kind: product
  actor: participant
  entities:
  - entity: audience-question
    effect: creates
    to: Open
    facts:
    - Text
    - Asked at
  contexts:
    web:
      place: web::audience::participant-view
- text: Everyone on the presentation sees the Audience question in the list, the most upvoted first
  kind: condition
  actor: participant
  entities:
  - entity: audience-question
    effect: reads
    facts:
    - Text
    - Upvoters
  - entity: presentation
    effect: reads
    facts:
    - Q&A visibility
  contexts:
    web:
      place: web::audience::participant-view
---

# Ask a question everyone reads

## Trigger

A participant wants to ask without raising their hand.

## Outcome

The question is in the room's list and others can upvote it.

## Edge cases

- When only the presenter reads the questions, the Participant sees their own questions and no one else's.
