---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer writes under the selected Slide in the editor and chooses Comment
  kind: actor
  actor: organizer
  entities:
  - entity: slide
    effect: reads
    facts:
    - Question
  contexts:
    web:
      place: web::studio::editor
- text: The Product adds the Slide comment
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
      place: web::studio::editor
---

# Comment from the editor

## Trigger

The owner reviews comments while editing.

## Outcome

The comment sits on the Slide it was written about.
