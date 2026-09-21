# Security

## Secret handling
- Supabase URL + anon key in `NEXT_PUBLIC_*` env vars (safe for frontend).
- Supabase service role key — server-side only, never in frontend code.
- AI API key (if used later) — server-side only.

## Permission model
- **v1 (demo-first):** no login wall. Permissive RLS — all reads/writes open. Seed data visible to anonymous visitors.
- **Lock-down sprint:** add auth (signup/login). Replace permissive policies with owner-scoped: `auth.uid() = user_id`. Each user sees only their own contacts.
- **Partner sharing (later):** read-only shared link with a token, no write access.

## Approved-tools rule
Agent uses named tools only (`needs_summary_generator`, `warmth_tagger`). No raw execution. Agent inherits the user's permissions — can only touch data the user owns.

## Audit principle
Every meaningful action is logged: contact create/update/delete, CSV import/export, needs summary generated. Log includes actor, timestamp, target, and details.
