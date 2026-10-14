---
availability:
- place: web::studio
- place: cli
domain: presenting
references:
- kind: code
  role: implementation
  target: src/components/Results.tsx#ResultsDisplay
- kind: code
  role: implementation
  target: server/services/presentations.ts#getSlideResults
- kind: code
  role: implementation
  target: server/services/presentations.ts#getAllResults
- kind: code
  role: implementation
  target: src/components/Leaderboard.tsx#Leaderboard
- kind: code
  role: implementation
  target: cli/commands.ts#runCommand
---

# View results

An organizer follows the live tally of each slide, whatever the reveal mode, or reads the results from the command line.
