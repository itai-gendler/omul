---
appliesTo:
- type: entity
  id: participant-feedback
  effect: reads
permits:
- actors:
  - administrator
references:
- kind: code
  role: implementation
  target: server/routes/admin.ts#createAdminFeedbackRoutes
---

# Only administrators read participants' feedback

The answers participants give after a session are read by the instance's administrators and by no organizer.
