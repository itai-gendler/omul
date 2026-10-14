---
kind: primary
routes:
  cli: Command line
steps:
- text: The Organizer runs omul create with a template id
  kind: actor
  actor: organizer
  entities: []
  contexts:
    cli:
      place: cli
- text: The Product creates a Presentation in Draft from that template
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: creates
    to: Draft
    facts:
    - Title
    - Join code
    - Pace
    - Language
    - Results visibility
    - Q&A enabled
    - Q&A visibility
    - Q&A approval
    - Reactions enabled
    - Chat enabled
    - Ask for names
    - Join bar shown
    - Theme
    - Own theme
    - Logo
    - Edit link
    - Owner
    - Created at
  - entity: slide
    effect: creates
    facts:
    - Type
    - Question
    - Options
    - Correct answers
    - Content
    - Position
    with: presentation
  contexts:
    cli:
      place: cli
- text: The client prints the presentation's id, join code and links
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
    - Join code
  contexts:
    cli:
      place: cli
---

# Create from a template on the command line

## Trigger

The Organizer starts every sprint review from the same template.

## Outcome

A draft from the template exists and its join code is printed.

## Edge cases

- An unknown template id is refused and nothing is created.
