---
singleton: true
references:
- kind: code
  role: implementation
  target: server/deck-generator.ts#deckGenerationAllowsAnonymous
- kind: code
  role: implementation
  target: server/feedback-store.ts#readFeedbackSettings
- kind: code
  role: implementation
  target: server/admins.ts
- kind: doc
  role: intent
  target: docs/deployment.md
---

# Deployment settings

The settings the operator gives the instance when deploying it.

## Information kept

- **Drafting provider** — whether a language model provider is configured for drafting presentations from a prompt
- **Anonymous drafting** — whether people without an account may draft presentations from a prompt
- **Feedback channel** — whether people can send feedback about omul from the app menu
- **Prompt share** — the share of eligible participants asked for their opinion after a session, or off
- **Prompt cooldown** — how many days a device waits before it is asked again
- **Administrator emails** — the account addresses that administer the instance
