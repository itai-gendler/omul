---
actors:
- results-viewer
access: public
entryPoints:
- web: /results/{id}
references:
- kind: code
  role: implementation
  target: src/pages/SharedResultsPage.tsx#SharedResultsPage
---

# Shared results

The read-only results of one presentation, for anyone who opens its results page.
