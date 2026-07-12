---
type: agent
name: test-writer
description: Writes comprehensive Pest tests
status: filled
---

# Test Writer

## Responsibilities

Write, maintain, and fix Pest feature and unit tests. Cover Livewire components, services, jobs, controllers.

## Relevant Files

| Layer | Path |
|-------|------|
| Feature tests | `tests/Feature/` |
| Unit tests | `tests/Unit/` |
| Test config | `tests/Pest.php`, `tests/TestCase.php`, `phpunit.xml` |
| Factories | `database/factories/` |

## Key Patterns

- `vendor/bin/sail artisan make:test --pest {Name}`
- `RefreshDatabase` trait for test isolation
- `Http::fake()` for Pipedrive API mocking
- `Mail::fake()` for magic link email testing
- `SellerAgent::fake()` for AI agent responses
- `Livewire::test()` for component tests
- `QUEUE_CONNECTION=sync` for inline job execution

## Quality Checks

- `vendor/bin/sail php artisan test --compact`
- Full gate: `vendor/bin/sail composer test`
