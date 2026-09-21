# Tasks

## Sprint 1 — Core Engine + CSV
**Goal:** Contact list works end-to-end with seeded data, no login.
- [ ] Create contacts table + permissive RLS + seed 5 demo rows
- [ ] Contact list page — search, filter by warmth, sort
- [ ] Add/edit/delete contact form with FORMHD fields + where/when met
- [ ] CSV import (upload → batch insert, column mapping)
- [ ] CSV export (all contacts → downloadable .csv)
- [ ] Loading / empty / error states on every screen
**DoD:** Add a contact with FORMHD data, see it in the list, export to CSV, re-import — round-trip preserves all fields.

## Sprint 2 — Needs Summary (v1 functional milestone)
**Goal:** Each lead shows a needs summary + warmth, ranked.
- [ ] Rule-based needs_summary generator (0.3 + 0.1/field)
- [ ] Warmth tagger (hot/warm/cold)
- [ ] Show needs summary + warmth on contact detail + list
- [ ] Sort list by warmth then confidence
- [ ] Regenerate summary on FORMHD edit
**DoD:** Open a contact with all FORMHD filled → needs summary + Hot tag visible. Sort list by warmth → Hot contacts on top.

## Sprint 3 — Lock It Down
**Goal:** Per-user data via auth + RLS.
- [ ] Auth pages (signup/login)
- [ ] Set user_id on create from auth.uid()
- [ ] Replace permissive policies with `auth.uid() = user_id`
- [ ] Two users can't see each other's contacts
**DoD:** Log in as user A, create contact, log out, log in as user B, don't see A's contact.

## Sprint 4 — Partner Sharing (later)
- [ ] Read-only shared link
- [ ] Follow-up reminders
- [ ] AI-powered needs summaries

## Gantt
```
S1 ████  Core + CSV
S2 ██    Needs summary  ← v1 functional
S3 ██    Lock down
S4 ████  Partners / later
```
