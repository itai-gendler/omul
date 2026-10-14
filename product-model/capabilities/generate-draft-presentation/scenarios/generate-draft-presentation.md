---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer describes the session in at most 500 characters and chooses Generate draft deck
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::draft-generator
- text: The Product sends only the prompt to the configured language model and turns its reply into a draft
  kind: product
  actor: organizer
  entities:
  - entity: deployment-settings
    effect: reads
    facts:
    - Drafting provider
  contexts:
    web:
      place: web::studio::draft-generator
- text: The Product creates a Presentation in Draft with those slides, none of their options marked correct
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
    - Position
    with: presentation
  contexts:
    web:
      place: web::studio::draft-generator
- text: The Product opens the draft in the editor
  kind: condition
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::editor
---

# Draft a presentation from a prompt

## Trigger

The Organizer has a topic but no time to write the questions.

## Outcome

A draft is open in the editor; marking the correct answers is the Organizer's first edit.

## Edge cases

- Nothing records that the presentation was drafted by a language model.
- Room settings such as pace, reveal mode, Q&A and theme take their ordinary defaults.
