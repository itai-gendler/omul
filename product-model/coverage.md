---
scope: The omul server, browser app and command-line client at this revision.
method: Static inspection of source, route contracts and the repository's own documentation; nothing was run.
covered:
- description: Server routes and services for presentations, live sessions, answers, Q&A, chat, sharing, comments and workspaces.
  paths:
  - server/routes/presentations.ts
  - server/routes/workspaces.ts
  - server/routes/templates.ts
  - server/services/
  - server/schemas.ts
  - server/templates.ts
  - server/coalesce.ts
- description: Results, segmentation, previews and exports.
  paths:
  - server/segmentation.ts
  - server/results-export.ts
  - server/deck-pdf.ts
  - server/preview.ts
- description: Drafting a presentation from a prompt.
  paths:
  - server/routes/deck-generation.ts
  - server/deck-generator.ts
- description: Accounts, sign-in, email verification and API keys.
  paths:
  - server/accounts.ts
  - server/admins.ts
  - src/auth.tsx
  - src/auth-client.ts
- description: Feedback about omul and the administrators' reading of it.
  paths:
  - server/routes/feedback.ts
  - server/feedback-store.ts
  - server/routes/admin.ts
  - src/feedback.ts
  - src/feedback-prompt.ts
- description: Browser pages, their components and client state.
  paths:
  - src/pages/
  - src/components/
  - src/store/
  - src/api.ts
  - src/router.ts
  - src/App.tsx
  - src/i18n.ts
  - src/types.ts
  - src/reactions.ts
- description: Command-line client.
  paths:
  - cli/
exclusions:
- description: Requirement catalog, task log, maintainer and contributor documentation.
  paths:
  - docs/
  - task/
  - CONTRIBUTING.md
  - CODE_OF_CONDUCT.md
  - CLA.md
  - SECURITY.md
- description: Build, packaging and deployment configuration.
  paths:
  - Dockerfile
  - compose.yaml
  - Caddyfile
  - flake.nix
  - flake.lock
  - .mise.toml
  - vite.config.ts
  - package.json
  - bunfig.toml
  - tsconfig.json
  - .github/
- description: Repository tooling for the requirement catalog and publication checks.
  paths:
  - scripts/
- description: Brand assets, licenses and the email and style presentation layers.
  paths:
  - public/
  - server/emails/
  - src/index.css
  - src/components/ui/
  - src/components/BrandMark.tsx
  - LICENSE-AGPL-3.0
  - LICENSE-COMMERCIAL
  - NOTICE.md
  - TRADEMARK.md
- description: Storage, process wiring and static file serving.
  paths:
  - server/db.ts
  - server/index.ts
  - server/routes/static.ts
  - server/keyed-lock.ts
  - server/store-path.ts
  - server/sibling-db-path.ts
  - server/test-preload.ts
  - src/storage.ts
  - src/index.tsx
  - src/index.html
unmapped:
- description: Administrators' two-step owner reassignment and its audit log.
  paths:
  - server/admin-events.ts
- description: The HTTP API as an interface of its own, its discovery index and the live event channel.
  paths:
  - server/routes/discovery.ts
  - server/ws.ts
  - src/store/useSessionSocket.ts
- description: Abuse limits on the account-free routes.
  paths:
  - server/rate-limit.ts
  - server/proxy-trust.ts
- description: Legal links and their placement.
  paths:
  - server/legal-links.ts
  - server/routes/legal.ts
  - src/components/LegalLinks.tsx
- description: Transactional email delivery.
  paths:
  - server/email.ts
- description: The agent skill that drives the command-line client.
  paths:
  - skills/omul/
- description: Startup checks of the signing secret and the public origin.
  paths:
  - server/auth-secret.ts
  - server/app-paths.ts
limitations: []
---

# Coverage
