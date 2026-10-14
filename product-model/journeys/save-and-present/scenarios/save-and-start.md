---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Organizer chooses Save Changes in the editor
  kind: actor
  actor: organizer
  capability: edit-presentation
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Product saves the Presentation's settings
  kind: product
  actor: organizer
  capability: edit-presentation
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Title
  contexts:
    web:
      place: web::studio::editor
- text: The Product returns to the presenter view
  kind: condition
  actor: organizer
  capability: edit-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Organizer chooses Start Presentation
  kind: actor
  actor: organizer
  capability: start-presentation
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product takes the Presentation live
  kind: product
  actor: organizer
  capability: start-presentation
  entities:
  - entity: presentation
    effect: changes
    from: Draft
    to: Live
    facts:
    - Current slide
    - Slide opened at
    - Session started at
    - Session ended at
  contexts:
    web:
      place: web::studio::presenter-view
---

# Save changes and start

## Trigger

The Organizer finished preparing.

## Outcome

The presentation is live with the saved changes.
