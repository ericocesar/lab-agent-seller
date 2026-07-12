---
type: skill
name: code-review
description: Code review standards
status: filled
---

# Code Review

## Review Criteria

1. **Typing**: All methods have explicit param + return types
2. **Promotion**: Constructor property promotion used
3. **Braces**: Curly braces on all control structures
4. **Service Layer**: Business logic in `app/Services/`, not Livewire
5. **Idempotency**: CRM imports use `updateOrCreate` by `external_id`
6. **Secrets**: API tokens use `encrypted` cast; magic link tokens `sha256` hashed
7. **Enumeration Safety**: Magic links never reveal match status
8. **PT-BR**: User-facing strings in Portuguese
9. **Tests**: New behavior has Pest tests
10. **Formatting**: `vendor/bin/sail bin pint --dirty --format agent` run
