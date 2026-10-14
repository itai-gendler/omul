---
appliesTo:
- type: entity
  id: slide
  facts:
  - Form fields
- type: capability
  id: submit-answer
references:
- kind: code
  role: implementation
  target: server/schemas.ts#FORM_ANSWER_MAX_LENGTH
- kind: doc
  role: intent
  target: docs/requirements/REQ061.md
---

# A form is taken only when its required fields are filled and each answer fits its field

A required field left blank, an email field without an email address, a choice outside the field's options or an answer over 200 characters refuses the whole form.
