---
domain: workspaces
relations:
- entity: presentation
  verb: owns
  cardinality: one-to-many
- entity: workspace-member
  verb: has
  cardinality: one-to-many
- entity: workspace-template
  verb: publishes
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredWorkspaceSchema
- kind: code
  role: implementation
  target: server/services/workspaces.ts#createWorkspace
---

# Workspace

A shared owner of presentations: a team's place, whose members run its presentations together.

## Information kept

- **Name** — the workspace's name
- **Default theme** — the built-in theme a presentation created in it starts with
- **Created at** — when it was created
