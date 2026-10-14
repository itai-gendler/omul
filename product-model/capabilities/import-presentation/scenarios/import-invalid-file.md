---
kind: validation
routes:
  web: Web
steps:
- text: The Organizer picks a file that is not valid JSON, or that lacks a title or its content
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::home
- text: Home says the file is invalid; nothing is created
  kind: condition
  entities: []
  contexts:
    web:
      place: web::studio::home
---

# Import a file that is not an export

## Trigger

The Organizer picks the wrong file.

## Outcome

Nothing is created.
