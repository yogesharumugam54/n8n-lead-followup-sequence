# n8n Follow-up Email Sequence

Sends up to three follow-up emails to leads and stops when they reply.

## How it works
- A Google Sheet is the source of truth (status, step, next_send, last_sent).
- Every 15 minutes the workflow finds leads that are due, sends the right email for their step, and moves next_send forward.
- A second flow watches the inbox and marks a lead as Replied, which stops the sequence.

## Why a sheet instead of Wait nodes
Wait nodes that hold items for days are fragile and invisible. A sheet shows every lead's state, survives restarts, and cannot send the same step twice.

## Setup
1. Import workflow.json and connect Gmail and Google Sheets.
2. Create the Leads tab with the headers in SETUP.md.
3. Edit the three email texts.

## Safety
- Only email people who contacted you.
- Every email includes an opt-out line.
- Duplicate sends are blocked by next_send.

MIT License