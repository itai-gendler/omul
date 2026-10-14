---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer enters the email address someone signed up with and picks Member, Admin or Owner
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: web::signed-in::workspace
- text: The Product adds them to the Workspace at that role
  kind: product
  actor: organizer
  entities:
  - entity: workspace-member
    effect: creates
    facts:
    - Role
    - Email
    - Name
    - Added at
  - entity: workspace
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::workspace
---

# Add a member

## Trigger

A new colleague joins the team.

## Outcome

The colleague finds the Workspace in their list and works on its presentations.

## Edge cases

- With no role chosen, the new member is a Member.
