---
appliesTo:
- type: entity
  id: presentation
  facts:
  - Results link
- type: capability
  id: view-shared-results
- type: capability
  id: create-results-link
- type: capability
  id: revoke-results-link
references:
- kind: code
  role: implementation
  target: server/services/presentations.ts#authorizeResultsLink
- kind: doc
  role: intent
  target: docs/api.md
  title: The shareable results link
---

# The results link opens the tallies and nothing else

Whoever holds a presentation's results link reads every tally as its editors do, changes nothing, and does not see who took part. Creating a new link or revoking it stops the old one at once.
