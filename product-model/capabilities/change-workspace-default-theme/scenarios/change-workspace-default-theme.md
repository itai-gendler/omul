---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer picks one of the built-in themes under New decks start in
  kind: actor
  actor: organizer
  entities:
  - entity: workspace
    effect: reads
    facts:
    - Default theme
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product saves the Workspace's default theme
  kind: product
  actor: organizer
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Default theme
  contexts:
    web:
      place: web::signed-in::workspace
---

# Change the default theme

## Trigger

The team adopts a house style.

## Outcome

New presentations in the workspace start in that theme; existing ones keep theirs.
