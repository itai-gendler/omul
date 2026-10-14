---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Delete on a presentation that has ended and confirms
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::home
- text: The Product deletes the Presentation with its slides, every Answer, Audience question and Chat message the room left, its shares and its comments
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: removes
    from: Ended
  - entity: slide
    effect: removes
    with: presentation
  - entity: answer
    effect: removes
    with: slide
  - entity: audience-question
    effect: removes
    from: Open
    with: presentation
  - entity: chat-message
    effect: removes
    with: presentation
  - entity: collaborator
    effect: removes
    with: presentation
  - entity: slide-comment
    effect: removes
    with: slide
  contexts:
    web:
      place: web::studio::home
---

# Delete a finished presentation

## Trigger

The Organizer cleans up after a session.

## Outcome

The presentation and everything the room left on it are gone; its join code no longer finds it.

## Edge cases

- Deleting cannot be undone.
