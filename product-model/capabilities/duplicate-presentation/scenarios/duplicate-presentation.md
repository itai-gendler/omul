---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Duplicate on one of their presentations
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    as: original
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::home
- text: The Product creates a copy in Draft titled as a copy, with the same slides under new identities and the same pace, language, reveal mode, Q&A and audience channel settings
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    as: copy
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
    - Reactions enabled
    - Chat enabled
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
    with: copy
  contexts:
    web:
      place: web::studio::home
- text: The Product opens the copy in the editor
  kind: condition
  actor: organizer
  entities:
  - entity: presentation
    as: copy
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::studio::editor
---

# Duplicate a presentation

## Trigger

The Organizer runs a variant of last week's session.

## Outcome

The copy is open in the editor with its own join code and nothing the room submitted to the original.
