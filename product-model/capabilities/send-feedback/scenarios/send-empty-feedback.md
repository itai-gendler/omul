---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer tries to send the form with neither a rating nor a comment
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio
- text: The form says to add a rating or a comment; nothing is stored
  kind: condition
  entities: []
  contexts:
    web:
      place: web::studio
---

# Send without a rating or comment

## Trigger

The Organizer pressed send by accident.

## Outcome

Nothing is stored.
