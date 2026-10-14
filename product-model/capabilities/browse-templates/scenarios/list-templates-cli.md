---
kind: primary
routes:
  cli: Command line
steps:
- text: The Organizer runs omul templates
  kind: actor
  actor: organizer
  entities: []
  contexts:
    cli:
      place: cli
- text: The client lists each template's id, title and category
  kind: condition
  actor: organizer
  entities: []
  contexts:
    cli:
      place: cli
---

# List templates from the command line

## Trigger

The Organizer needs a template id for omul create.

## Outcome

The Organizer has the id.
