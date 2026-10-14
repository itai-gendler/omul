---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Share the results and chooses Create link
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product creates a read-only results link, copies it and shows when it was created
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Results link
    - Results link created at
  contexts:
    web:
      place: web::studio::presenter-view
---

# Create a results link

## Trigger

A stakeholder who was not in the room wants the results.

## Outcome

The Organizer can hand the link to anyone.
