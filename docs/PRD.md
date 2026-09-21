# Contact List — PRD

**Problem:** I can't keep track of my leads' personal details and needs. I want to log each contact using the FORMHD framework (Family, Occupation, Recreation, Money, Hobbies, Dreams) plus where/when we met, so I know what each lead actually needs.

**Target user:** Me — a solo operator who shares contact info with business partners.

## Core objects
- **Contact** — name, email, phone, where/when met, FORMHD fields, needs summary, warmth tag.
- **CSV import/export** — move data between Excel and the app.

## MVP (v1 checklist)
- [ ] Contact list with search + filter by warmth
- [ ] Add / edit / delete a contact with all FORMHD fields
- [ ] Track where & when we met
- [ ] CSV import (Excel → app)
- [ ] CSV export (app → Excel)
- [ ] Rule-based needs summary generated from FORMHD data
- [ ] Lead warmth tag (Hot / Warm / Cold)
- [ ] Demo data visible without login

## Non-goals (v1)
- Login / user accounts
- Multi-user collaboration
- Automated follow-up scheduling
- Mobile native app

## Success criteria
After one week I open my contact list, each lead shows their FORMHD profile + a needs summary + warmth tag, I can sort by warmth, and I can export the full enriched list to Excel and re-import it without losing data.
