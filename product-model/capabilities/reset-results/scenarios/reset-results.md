---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Reset results and confirms Clear results
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product deletes every Answer and upvote, every Audience question and Chat message, forgets the names participants gave, and returns the Presentation to Draft at its start
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    from: Ended
    to: Draft
    facts:
    - Current slide
    - Slide opened at
    - Revealed slides
    - Closed slides
    - Screen blanked
    - Session started at
    - Session ended at
  - entity: answer
    effect: removes
  - entity: audience-question
    effect: removes
    from: Open
  - entity: chat-message
    effect: removes
  - entity: participant
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::studio::presenter-view
---

# Clear the results

## Trigger

The Organizer runs the same presentation for a second group.

## Outcome

The presentation is a clean draft with the same slides, settings and join code.

## Edge cases

- A live presentation can be reset too; the room goes back to waiting.
