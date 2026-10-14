---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Share the results and chooses Revoke
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Results link
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product revokes the link
  kind: product
  actor: organizer
  entities:
  - entity: presentation
    effect: changes
    facts:
    - Results link
    - Results link created at
  contexts:
    web:
      place: web::studio::presenter-view
---

# Revoke the results link

## Trigger

The results should no longer be shared.

## Outcome

Every copy of the link stops working; whoever opens it is told it is no longer valid.
