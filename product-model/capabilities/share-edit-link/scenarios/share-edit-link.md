---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Share with edit permissions and Copy edit link
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Edit link
  contexts:
    web:
      place: web::studio::presenter-view
- text: The edit link is on the clipboard
  kind: condition
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Copy the edit link

## Trigger

A co-host will run the session from their own laptop.

## Outcome

Whoever opens the link keeps its edit permission in their browser and can edit and run the presentation.

## Edge cases

- A presentation a workspace owns has no edit link to share.
