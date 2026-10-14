---
kind: primary
routes:
  cli: Command line
steps:
- text: The Organizer runs omul list
  kind: actor
  actor: organizer
  entities: []
  contexts:
    cli:
      place: cli
- text: The client lists the presentations the Organizer owns, with their join codes
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Join code
    - Created at
  contexts:
    cli:
      place: cli
---

# List presentations from the command line

## Trigger

The Organizer needs the id of a presentation to read its results.

## Outcome

The Organizer has the id and join code.

## Edge cases

- Without an API key, omul list stops before asking the server and says how to configure one.
