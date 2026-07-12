---
type: skill
name: refactoring
description: Safe code refactoring
status: filled
---

# Refactoring

## Approach

1. **Understand**: Read the code and its tests
2. **Test coverage**: Ensure tests cover the area
3. **Small steps**: One refactor at a time
4. **Verify**: Tests pass after each step

## Common Patterns

- Extract service methods from Livewire components
- Replace duplicate queries with model scopes
- Introduce DTO/value objects for complex data
- Extract driver interface for new CRM providers
- Migrate DB-status fields to `Concerns\IsLookup`

## Safety

- `vendor/bin/sail composer test` before and after
- Never change tests first (they are the safety net)
- Keep commits atomic per refactor step
