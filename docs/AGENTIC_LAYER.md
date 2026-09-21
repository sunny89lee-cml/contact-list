# Agentic Layer

## Risk levels

### Low — auto (no approval)
- Generate needs_summary from FORMHD fields on contact save.
- Assign warmth tag (hot/warm/cold).

### Medium — light approval (later)
- Draft follow-up message from needs_summary.
- Update contact status after a meeting.

### High — always approval (later)
- Send a message to a contact.

### Critical — human-only
- Delete a contact.
- Export CSV (data leaves the system).

## Named tools (v1)
- `needs_summary_generator` — reads FORMHD fields, returns summary text + confidence.
- `warmth_tagger` — reads FORMHD fields, returns hot/warm/cold.

No raw tool execution. Agent never calls `run_any` / `send_any`.

## Audit-log fields
action · actor · target_contact_id · timestamp · details (JSON).

## v1 vs later
- **v1:** needs_summary + warmth auto-generated on save. No external actions.
- **Later:** draft follow-ups (medium), send messages (high), scheduled reminders.
