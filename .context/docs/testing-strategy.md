---
type: doc
name: testing-strategy
description: Test frameworks, patterns, coverage requirements, and quality gates
category: testing
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Testing Strategy

## Test Types

- **Feature tests** (Pest): 20 files in `tests/Feature/` covering Livewire components, HTTP controllers, jobs, services
- **Unit tests**: in `tests/Unit/`
- **Livewire tests**: `Livewire::test()` for component interactions, state validation, streaming
- **Service tests**: Direct service method calls with mocked dependencies

## Running Tests

```sh
# All tests
vendor/bin/sail php artisan test --compact

# Single test
vendor/bin/sail php artisan test --compact --filter=testName

# Full quality gate (lint + types + test)
vendor/bin/sail composer test
```

## Quality Gates

- `composer lint:check` — Laravel Pint formatting check
- `composer types:check` — PHPStan level 7 (larastan)
- `composer test` — Full gate: `config:clear` + `lint:check` + `types:check` + `php artisan test`
- All tests must pass before merge

## Testing Tools

| Tool | Purpose |
|------|---------|
| Pest 4 | Test runner |
| PHPUnit 12 | Underlying framework |
| Mockery | Mocking framework |
| `Http::fake()` | HTTP facade faking |
| `Mail::fake()` | Mail faking |
| `SellerAgent::fake()` | AI agent faking |
| `fakerphp/faker` | Fake data generation |

## Troubleshooting

- Tests use `QUEUE_CONNECTION=sync` so jobs run inline
- `refreshDatabase` trait used for database isolation
- `Http::fake()` captures Pipedrive API calls

## Related Resources

- [Development Workflow](development-workflow.md)
