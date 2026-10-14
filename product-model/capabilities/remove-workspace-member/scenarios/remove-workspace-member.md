---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Remove beside a Workspace member and confirms
  kind: actor
  actor: organizer
  entities:
  - entity: workspace-member
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product removes the membership; the Workspace's presentations are untouched
  kind: product
  actor: organizer
  entities:
  - entity: workspace-member
    effect: removes
  - entity: workspace
    effect: reads
    facts: []
  - entity: presentation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Remove a member

## Trigger

A colleague left the team.

## Outcome

That person's next request on the workspace's presentations is refused.
