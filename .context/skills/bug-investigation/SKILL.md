---
type: skill
name: bug-investigation
description: Systematic bug investigation
status: filled
---

# Bug Investigation

## Workflow

1. Reproduce with a failing Pest test
2. Check logs: `vendor/bin/sail artisan pail` (Laravel Pail for real-time logs)
3. Inspect browser logs via Laravel Boost MCP: `browser-logs`
4. Check database state: `vendor/bin/sail artisan tinker` or MCP `database-query`
5. Isolate the layer (Livewire component, service, job, AI agent)
6. Write fix + verify test passes
7. Run full suite: `vendor/bin/sail composer test`

## Common Issues

- Scan failures: check Pipedriver API responses, token validity, rate limits
- Magic links: verify hash matching, expiry, email normalization
- Chat streaming: mock `SellerAgent`, check `TextDelta` events
- Gate/auth: ensure correct guard (`auth:client` vs `auth`)
