---
type: cli
actors:
- organizer
languages:
- en
references:
- kind: code
  role: implementation
  target: cli/commands.ts#runCommand
- kind: doc
  role: intent
  target: docs/api.md
  title: Driving the API from a terminal
- kind: doc
  role: context
  target: skills/omul/SKILL.md
---

# omul command-line client

The `omul` command an organizer uses to create a presentation and read its results back without a browser, signed in with a personal API key.
