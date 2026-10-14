---
kind: primary
routes:
  cli: Command line
steps:
- text: The Organizer runs omul create with a title and a deck file
  kind: actor
  actor: organizer
  entities: []
  contexts:
    cli:
      place: cli
- text: The Product creates the Presentation in Draft with those slides and its own join code
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

# Create a presentation from a deck file

## Trigger

The Organizer scripts the presentations they run every week.

## Outcome

The presentation is a draft the Organizer can open in the browser and run.

## Decision points

### Does the client carry an API key?

Who the presentation belongs to.

- With an API key → the key's account owns it, and no edit link is made
- Without one → it has no owner, and the client keeps its edit link on this machine

## Edge cases

- omul create without --deck or --template stops before asking the server and says a deck has to come from somewhere.
