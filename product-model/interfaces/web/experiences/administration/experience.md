---
actors:
- administrator
access: restricted
entryPoints:
- web: /app/admin/feedback
references:
- kind: code
  role: implementation
  target: src/pages/AdminFeedbackPage.tsx#AdminFeedbackPage
---

# Administration

The pages only the instance's administrators may enter.
