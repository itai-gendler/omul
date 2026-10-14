---
availability:
- place: web::studio
domain: presenting
references:
- kind: code
  role: implementation
  target: src/components/ExportDialog.tsx#ExportDialog
- kind: code
  role: implementation
  target: server/results-export.ts#buildResultsWorkbook
- kind: code
  role: implementation
  target: server/deck-pdf.ts#buildDeckDocument
- kind: doc
  role: intent
  target: docs/requirements/REQ095.md
- kind: doc
  role: intent
  target: docs/requirements/REQ096.md
---

# Export session

An organizer downloads a session as a spreadsheet, as a PDF with results, or as a PDF of the deck alone.
