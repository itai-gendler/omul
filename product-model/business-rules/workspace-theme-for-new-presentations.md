---
appliesTo:
- type: entity
  id: workspace
  facts:
  - Default theme
- type: capability
  id: change-workspace-default-theme
- type: capability
  id: create-workspace-presentation
references:
- kind: code
  role: implementation
  target: server/services/workspaces.ts#defaultDeckThemeFor
---

# A workspace's default theme applies only to presentations created in it afterwards

Changing the default theme changes no existing presentation, and a presentation moved in keeps its own theme.
