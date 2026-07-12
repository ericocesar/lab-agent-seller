---
type: doc
name: development-workflow
description: Day-to-day engineering processes, branching, and contribution guidelines
category: workflow
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Development Workflow

## Branching & Releases

Trunk-based development on `main`. Feature branches for non-trivial changes. All commits must pass `composer test` (`config:clear` + `lint:check` + `types:check` + `php artisan test`).

## Local Development

All commands run through Laravel Sail:

```sh
# Start services
vendor/bin/sail up -d

# Install dependencies
vendor/bin/sail composer install
vendor/bin/sail npm install

# Run migrations
vendor/bin/sail artisan migrate

# Build assets
vendor/bin/sail npm run build

# Dev server
vendor/bin/sail npm run dev

# Run tests
vendor/bin/sail php artisan test --compact

# Run one test
vendor/bin/sail php artisan test --compact --filter=testName

# Full quality gate
vendor/bin/sail composer test
```

## Code Review Expectations

- Ensure formatting passes: `vendor/bin/sail bin pint --dirty --format agent`
- Ensure static analysis passes level 7
- All tests must pass (Pest feature tests + Livewire component tests)
- Never leave PHP unformatted — Pint and PHPStan block `composer test`

## Related Resources

- [Testing Strategy](testing-strategy.md)
- [Tooling](tooling.md)
