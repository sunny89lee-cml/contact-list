# Test Plan

## v1 success scenario
1. Open app → 5 seeded contacts visible in list with warmth tags.
2. Click **Import** → upload `sample.csv` → new contacts appear in list.
3. Click a contact → fill all 6 FORMHD fields + where/when met → **Save**.
4. Contact detail shows needs_summary + **Hot** warmth tag.
5. Return to list → sort by warmth → Hot contacts on top.
6. Click **Export** → CSV downloads → open in Excel → all contacts + FORMHD fields present.
7. Re-import that CSV → no data lost.

## Empty states
- Zero contacts → "No contacts yet. Add one or import a CSV."
- Search no match → "No contacts match your search."
- Filter Cold with no Cold leads → "No cold leads."

## Error states
- Upload non-CSV file → "Please upload a .csv file."
- Save without name → "Name is required."
- Supabase unreachable → "Couldn't save. Check your connection and try again."
- Malformed CSV → "Row 3 skipped: missing name."

## Loading states
- List loading → skeleton rows.
- Import processing → "Importing contacts…" with count.
- Needs summary generating → spinner on contact card.
- Export building → "Preparing your CSV…"
