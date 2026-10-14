---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses Replace link
  kind: actor
  actor: organizer
  entities:
  - entity: presentation
    effect: reads
    facts:
    - Results link created at
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product creates a new results link; the old one stops opening anything
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

# Replace the results link

## Trigger

The link reached people it should not have.

## Outcome

Only the new link opens the results.
