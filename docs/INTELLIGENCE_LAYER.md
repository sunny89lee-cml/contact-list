# Intelligence Layer

## Messy inputs
- Free-text FORMHD notes (varying length, abbreviations).
- CSV column names differ ("Name" vs "Full Name", "Where Met" vs "met_location").
- Inconsistent phone/email formats.

## Auto-structure schema
```json
{
  "name": "Sarah Chen",
  "email": "sarah@example.com",
  "phone": "555-0101",
  "met_where": "Tech conference",
  "met_when": "2024-09-15",
  "family": "Married, 1 daughter",
  "occupation": "Software engineer",
  "recreation": "Rock climbing",
  "money": "Looking to invest in real estate",
  "hobbies": "Photography",
  "dreams": "Financial independence by 45",
  "needs_summary": "Interested in real estate investing; values family time and work-life balance.",
  "needs_confidence": 0.85,
  "needs_source": "FORMHD-rule-based"
}
```

## Events to track
contact_created, contact_updated, needs_summary_generated, csv_imported, csv_exported.

## Scoring rules (v1, rule-based)
- **needs_confidence** = 0.3 base + 0.1 per filled FORMHD field (max 0.9).
- **Warmth:**
  - **Hot** — money + dreams both filled.
  - **Warm** — 4+ FORMHD fields filled.
  - **Cold** — fewer than 4 fields.

## What gets ranked
Contact list sorted by warmth (Hot → Warm → Cold), then by needs_confidence descending.

## v1 vs later
- **v1:** rule-based needs summary + warmth.
- **Later:** AI-generated nuanced summaries, follow-up suggestions, auto-tag from occupation/hobbies.
