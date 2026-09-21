# Architecture

**Stack:** Next.js 14 (App Router) · Supabase (Postgres) · Vercel.

## Build now vs later
- **Now:** contacts CRUD, FORMHD fields, CSV import/export, rule-based needs summary, warmth scoring.
- **Later:** login + owner-scoped data, partner read-only sharing, AI-powered summaries, follow-up reminders.

## Key user action flow
1. Open app → contact list loads (seeded demo rows).
2. Click **Import** → upload CSV → contacts created.
3. Click a contact → fill FORMHD fields → Save.
4. Needs summary + warmth auto-generated from FORMHD → shown on card.
5. Click **Export** → CSV downloads → opens in Excel.

## Nav shell
Left sidebar on desktop (Contacts, Import / Export) → hamburger menu on mobile. Current section highlighted.

## Layers
1. **Data** — contacts table + Supabase queries.
2. **Logic** — CRUD, CSV parse/build, warmth scoring.
3. **Smart** — needs summary generation.

Core list/add/edit/export works with the AI layer off.

## Repo structure
```
app/contacts/        pages: list, [id], new
app/import-export/   upload + download
components/           contact-form, contact-list, csv-uploader
lib/data/            contacts.ts — all DB reads/writes
lib/csv/             import.ts, export.ts
lib/ai/              needs-summary.ts
tests/               beside each module
```

## Module map
1. **contacts-data** — owns contacts table, all CRUD. Build first.
2. **csv-io** — parse/build CSV, batch insert. Build second.
3. **needs-summary** — rule-based needs text + warmth from FORMHD. Build third.
4. **contact-ui** — list, form, detail, import/export screens. Build fourth.
