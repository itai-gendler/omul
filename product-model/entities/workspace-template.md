---
domain: workspaces
references:
- kind: code
  role: implementation
  target: server/schemas.ts#StoredWorkspaceTemplateSchema
- kind: code
  role: implementation
  target: server/services/workspace-templates.ts#publishWorkspaceTemplate
---

# Workspace template

A presentation a workspace publishes for its members to start new presentations from.

## Information kept

- **Title** — the name in the workspace's gallery
- **Description** — what it is for
- **Category** — Meetings, Workshops, Teaching, Feedback or Engagement
- **Tags** — up to ten tags
- **Slides** — a copy of the source presentation's slides as they were when published
- **Published by** — the member who published it
- **Published at** — when it was last published
