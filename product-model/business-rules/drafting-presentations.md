---
appliesTo:
- type: entity
  id: presentation
  effect: creates
  contexts:
  - place: web::studio::draft-generator
permits:
- related:
  - verb: owns
    entity: organizer
  when:
  - entity: deployment-settings
    fact: Drafting provider
    is: Configured
- actors:
  - organizer
  when:
  - entity: deployment-settings
    fact: Drafting provider
    is: Configured
  - entity: deployment-settings
    fact: Anonymous drafting
    is: 'On'
references:
- kind: code
  role: implementation
  target: server/routes/deck-generation.ts#createDeckGenerationRoutes
- kind: code
  role: implementation
  target: server/deck-generator.ts#deckGenerationAllowsAnonymous
---

# Drafting from a prompt needs a configured provider, and an account unless the deployment allows otherwise

A presentation is drafted from a prompt only while the deployment configures a language model provider, and only for a signed-in organizer, who owns the draft, unless the deployment allows anonymous drafting.

## Rationale

Each draft spends the operator's language model budget.
