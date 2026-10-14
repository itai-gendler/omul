---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer approves a question that is awaiting approval
  kind: actor
  actor: organizer
  entities:
  - entity: audience-question
    effect: reads
    facts:
    - Text
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product publishes the Audience question to the room
  kind: product
  actor: organizer
  entities:
  - entity: audience-question
    effect: changes
    from: Awaiting approval
    to: Open
    facts: []
  contexts:
    web:
      place: web::studio::presenter-view
---

# Approve a question

## Trigger

A participant asked something worth taking.

## Outcome

The question joins the room's list and can be upvoted.

## Edge cases

- Approval is one-way: an approved question is not sent back to waiting.
