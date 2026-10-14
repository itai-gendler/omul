---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Sign out
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::signed-in
- text: The Product ends the Organizer's session
  kind: product
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::signed-in
---

# Sign out

## Trigger

The Organizer is done on a shared computer.

## Outcome

The Organizer is signed out. Home shows only the presentations whose edit link this browser holds.
