---
type: skill
name: pr-review
description: Pull request review
status: filled
---

# PR Review

## Checklist

- [ ] Code follows existing conventions and patterns
- [ ] No N+1 queries; eager loading used where needed
- [ ] All user-facing strings are PT-BR
- [ ] API tokens encrypted; magic link tokens hashed
- [ ] Tests cover new/changed behavior
- [ ] `vendor/bin/sail composer test` passes
- [ ] `vendor/bin/sail bin pint --dirty --format agent` run
- [ ] No secrets in code
- [ ] Routes use named routes where applicable
- [ ] Permissions/guards correct (`auth:client` vs `auth`)
