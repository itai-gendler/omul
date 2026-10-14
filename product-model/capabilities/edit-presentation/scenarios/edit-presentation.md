---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer changes the title or the settings in the editor
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Organizer chooses Save Changes
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::editor
- text: The Product saves the changes and sends them to everyone already in the room
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Title
    - Pace
    - Language
    - Results visibility
    - Q&A enabled
    - Q&A visibility
    - Reactions enabled
    - Chat enabled
    - Ask for names
    - Theme
    - Own theme
    - Logo
  contexts:
    web:
      place: web::studio::editor
- text: The Product returns to the presenter view
  kind: condition
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::presenter-view
---

# Change the presentation's settings

## Trigger

The Organizer prepares a presentation for a different audience.

## Outcome

The presentation runs with the new settings; participants already joined see them at once.

## Edge cases

- A new theme, logo or own colors apply to the presenter view and to every participant's screen.
