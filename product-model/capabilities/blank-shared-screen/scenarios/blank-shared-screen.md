---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Blank the shared screen
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product puts a curtain over the shared screen
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Screen blanked
  contexts:
    web:
      place: web::studio::presenter-view
---

# Blank the shared screen

## Trigger

The Organizer wants the room's attention off the wall.

## Outcome

The shared screen shows that it is blank. Participants' own devices keep their question and can still answer.

## Edge cases

- The screen stays blank while the Organizer moves to another slide, and after a reload.
