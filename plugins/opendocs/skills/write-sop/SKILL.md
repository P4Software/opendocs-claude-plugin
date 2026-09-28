---
name: write-sop
description: Write a standard operating procedure (SOP), work instruction or process document and publish it to OpenDocs. Use when the user asks to write, document, standardize or formalize a process, procedure, checklist, policy or how-we-do-X document for a team.
---

Write an SOP the team can follow without asking questions, then save it to OpenDocs with the OpenDocs connector (if its tools are missing, ask the user to connect OpenDocs first).

## 1. Gather what you need

Ask only for what the user hasn't given: the process name, who performs it, what triggers it, the steps as they do them today, tools or systems used, and what record or output it produces. If the user pastes notes or a transcript, extract these from it.

## 2. Write it in this structure

- **Purpose**: one or two sentences on why the procedure exists
- **Scope**: what it covers and what it doesn't
- **Roles**: who does what (role names, not people's names, unless the user wants names)
- **Definitions**: terms a new team member might not know
- **Procedure**: numbered steps, one action per step, each starting with a verb; note decision points as "If X, go to step N"
- **Records**: what is saved, where, and for how long
- **Related documents**: links to other pages
- **Revision history**: version, date, summary of change

Use the team's own wording for systems and roles. Mark anything the user didn't confirm as "To confirm" instead of guessing.

## 3. Save it to OpenDocs

Call `list_spaces` and suggest a space (for example Operations or Quality), check `search_pages` for an existing SOP on the same process, show the draft, then create or update the page. Publish only when the user asks.

Teams on the OpenDocs Compliance plan can then send the page for review and approval and assign it for read acknowledgment in the OpenDocs app; mention this when the user works in a regulated area (health, food, manufacturing, finance).
