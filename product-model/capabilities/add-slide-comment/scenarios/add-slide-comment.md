---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer writes on the current Slide's comments and chooses Comment
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product adds the Slide comment under the Organizer's display name
  kind: product
  actor: organizer
  entities:
  - entity: slide-comment
    effect: creates
    facts:
    - Body
    - Author name
    - Written at
  - entity: slide
    effect: reads
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Comment on a slide

## Trigger

A reviewer has a suggestion about one question.

## Outcome

Everyone the presentation is shared with reads the comment on that Slide.
