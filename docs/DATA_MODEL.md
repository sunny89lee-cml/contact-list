# Data Model

## contacts
| field | type | notes |
|---|---|---|
| id | uuid PK | `gen_random_uuid()` |
| user_id | uuid | nullable — future owner scoping |
| name | text | not null |
| email | text | |
| phone | text | |
| met_where | text | where we met |
| met_when | date | when we met |
| family | text | FORMHD — F |
| occupation | text | FORMHD — O |
| recreation | text | FORMHD — R |
| money | text | FORMHD — M |
| hobbies | text | FORMHD — H |
| dreams | text | FORMHD — D |
| needs_summary | text | AI-generated |
| needs_source | text | e.g. "FORMHD-rule-based" |
| needs_confidence | numeric | 0–1 |
| needs_review_status | text | default 'unreviewed' |
| warmth | text | hot / warm / cold |
| tags | text[] | |
| created_at | timestamptz | default now() |

**Relationships:** standalone in v1 (no FKs).

**RLS:** enabled. v1 permissive policies (open read/write) so demo works without login. Lock-down sprint replaces with `auth.uid() = user_id`.

**AI fields:** needs_summary + needs_source + needs_confidence + needs_review_status. warmth is rule-derived (stored for quick filtering).

Secondary tables (later): `import_logs`, `follow_ups` — not in v1 migration.
