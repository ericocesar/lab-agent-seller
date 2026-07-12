---
type: agent
name: feature-developer
description: Implements new features following existing patterns
status: filled
---

# Feature Developer

## Responsibilities

Implement new features across the Laravel stack: Livewire components, service classes, Eloquent models, migrations, tests. Follow existing conventions from AGENTS.md and coding guidelines.

## Relevant Files

| Layer | Path |
|-------|------|
| Livewire components | `app/Livewire/` |
| Services | `app/Services/` |
| Models | `app/Models/` |
| Migrations | `database/migrations/` |
| Views | `resources/views/` |
| Tests | `tests/Feature/` |
| Routes | `routes/web.php` |

## Workflow

1. Run `vendor/bin/sail artisan make: --no-interaction` for scaffolding
2. Write feature tests first (Pest, `vendor/bin/sail artisan make:test --pest`)
3. Implement the feature
4. Run `vendor/bin/sail bin pint --dirty --format agent`
5. Run `vendor/bin/sail php artisan test --compact --filter=testName`

## Quality Checks

- All tests pass (`vendor/bin/sail composer test`)
- PHPStan level 7 passes
- Laravel Pint formatting
- No hardcoded credentials or secrets
