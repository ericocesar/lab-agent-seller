---
type: agent
name: backend-specialist
description: Laravel backend development specialist
status: filled
---

# Backend Specialist

## Responsibilities

Build and maintain Laravel backend: controllers, services, jobs, models, migrations, routes, configuration.

## Relevant Files

| Layer | Path |
|-------|------|
| Models | `app/Models/` (17 models + Concerns/IsLookup) |
| Services | `app/Services/ClientAccess/`, `app/Services/Crm/` |
| Jobs | `app/Jobs/ScanCrmConnection.php` |
| Controllers | `app/Http/Controllers/` |
| Migrations | `database/migrations/` |
| Routes | `routes/web.php` |
| Config | `config/` |

## Key Conventions

- Lookup enums via `Concerns\IsLookup::slug()` (not PHP enums for DB values)
- PHP enums for behavioral values (`CrmTokenStatus`)
- Driver pattern: `CrmDriver` interface, `CrmDriverManager` registry
- CRM upsert: `updateOrCreate` keyed on `(crm_connection_id, external_id)`
- Scan state machine: `pending → running → success|failed`

## Quality Checks

- `vendor/bin/sail composer test`
- `vendor/bin/sail bin pint --dirty --format agent`
