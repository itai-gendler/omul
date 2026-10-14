---
kind: person
acts: external
relations:
- entity: presentation
  verb: owns
  cardinality: one-to-many
- entity: presentation
  verb: holds-edit-link-for
  cardinality: many-to-many
- entity: account
  verb: has
  cardinality: one-to-one
- entity: collaborator
  verb: holds
  cardinality: one-to-many
- entity: workspace-member
  verb: holds
  cardinality: one-to-many
- entity: slide-comment
  verb: writes
  cardinality: one-to-many
- entity: chat-message
  verb: sends
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#resolveDeckAccess
- kind: doc
  role: intent
  target: docs/api.md
  title: Auth model
---

# Organizer

A person who builds presentations and runs them in front of a room, with or without an account. Without an account they act on the presentations whose edit link their browser holds; with one they also own presentations, work on presentations shared with them and take part in workspaces.
