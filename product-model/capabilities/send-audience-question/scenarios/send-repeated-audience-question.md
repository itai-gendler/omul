---
kind: alternative
routes:
  web: Web
steps:
- text: The Participant sends a question another participant already asked, word for word
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product counts it as an upvote on the existing Audience question instead of adding another
  kind: product
  actor: participant
  entities:
  - entity: audience-question
    effect: changes
    facts:
    - Upvoters
  contexts:
    web:
      place: web::audience::participant-view
---

# Ask a question someone already asked

## Trigger

Two people wonder the same thing.

## Outcome

The room's list holds the question once, with one more upvote.

## Edge cases

- Sending one's own question again adds nothing: the Participant is told they already asked it.
