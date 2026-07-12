---
type: agent
name: database-specialist
description: Database schema and migration specialist
status: filled
---

# Database Specialist

## Responsibilities

Design and maintain database schemas, write migrations, optimize queries, manage seeders.

## Relevant Files

| Layer | Path |
|-------|------|
| Migrations | `database/migrations/` (19 files) |
| Models | `app/Models/` (17 models) |
| Seeders | `database/seeders/LookupSeeder.php` |
| Factories | `database/factories/` |

## Schema Conventions

- Engine: Postgres 18 (Sail) / SQLite (local)
- Lookup tables: `Concerns\IsLookup` trait, seeded by `slug`
- Unique constraints: `(crm_connection_id, external_id)` for CRM entities
- `encrypted` cast for `crm_connections.api_token`
- `hashed` cast for `users.password`
- Indexed: `crm_persons.email` (tenant matching), `magic_links.email`, `magic_links.token`

## Key Tables

- `crm_connections` — one per company, unique `user_id`
- `magic_links` — `token` (unique sha256), `expires_at`, `used_at?`
- `conversations` — unique `(client_id, user_id)`
- `messages` — ordered by `id` as chronological turns
