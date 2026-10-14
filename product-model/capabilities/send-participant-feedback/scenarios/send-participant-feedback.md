---
kind: primary
routes:
  web: Web
steps:
- text: The presentation has ended; the Participant saw it live, falls in the share the deployment asks and was not asked within the cooldown
  kind: condition
  actor: participant
  entities:
  - entity: deployment-settings
    effect: reads
    facts:
    - Prompt share
    - Prompt cooldown
  - entity: presentation
    effect: reads
    facts:
    - Session started at
  contexts:
    web:
      place: web::audience::participant-view
- text: The Participant gives a rating, a comment or both and chooses Send
  kind: actor
  actor: participant
  entities: []
  contexts:
    web:
      place: web::audience::participant-view
- text: The Product stores the rating and comment with only the language and the day, for the people who run omul here
  kind: product
  actor: participant
  entities:
  - entity: participant-feedback
    effect: creates
    facts:
    - Rating
    - Comment
    - Language
    - Sent on
  contexts:
    web:
      place: web::audience::participant-view
---

# Answer the prompt after a session

## Trigger

The session the Participant attended has ended.

## Outcome

The people who run the instance can read what the Participant thinks; the organizers of the session cannot.
