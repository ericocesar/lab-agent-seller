---
type: agent
name: bug-fixer
description: Investigates and fixes bugs systematically
status: filled
---

# Bug Fixer

## Responsibilities

Debug and fix issues across the full stack: Livewire components, service layer, jobs, AI agent, database queries. Reproduce via existing tests or write new failing tests first.

## Relevant Files

| Area | Path |
|------|------|
| Livewire | `app/Livewire/` |
| Services | `app/Services/` |
| Jobs | `app/Jobs/` |
| Models | `app/Models/` |
| AI Agent | `app/Ai/Agents/` |
| Tests | `tests/Feature/` |

## Workflow

1. Write a failing test that reproduces the bug
2. Identify root cause (check logs, queries, HTTP fakes)
3. Fix the code
4. Verify test passes
5. Run full test suite
6. Run `vendor/bin/sail bin pint --dirty --format agent`

## Common Bug Patterns

- CRM scan failures: check `PipedriveDriver` HTTP responses, scan state machine (`pending → running → success|failed`)
- Magic link issues: check `sha256` hash matching, expiry, email normalization
- Chat streaming: check `SellerAgent::fake()`, `TextDelta` event handling
- Auth guard mismatch: `auth:client` vs `auth` guard
