---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer opens Export this session and picks Spreadsheet (.xlsx)
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::studio::presenter-view
- text: The Product downloads a workbook with every Answer, the per-participant matrix and every tally
  kind: product
  actor: organizer
  entities:
  - entity: answer
    effect: reads
    facts:
    - Value
    - Statement
    - Skipped
    - Submitted at
  - entity: participant
    effect: reads
    facts:
    - Name
  - entity: slide
    effect: reads
    facts:
    - Question
    - Options
  contexts:
    web:
      place: web::studio::presenter-view
---

# Export a spreadsheet

## Trigger

The Organizer analyses the session afterwards.

## Outcome

The Organizer has a workbook of the whole session.
