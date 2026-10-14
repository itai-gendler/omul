---
appliesTo:
- type: entity
  id: feedback
  effect: reads
permits:
- actors:
  - administrator
references:
- kind: code
  role: implementation
  target: server/routes/admin.ts#createAdminFeedbackRoutes
- kind: code
  role: implementation
  target: server/admins.ts
---

# Only administrators read the feedback sent about omul

Feedback from the app menu is read by the instance's administrators and by no organizer.
