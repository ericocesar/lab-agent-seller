---
type: skill
name: commit-message
description: Commit message conventions
status: filled
---

# Commit Messages

## Format

Conventional commits with scope detection.

### Types
- `feat:` — New feature
- `fix:` — Bug fix
- `refactor:` — Code refactoring
- `test:` — Test changes
- `chore:` — Maintenance
- `docs:` — Documentation

### Scope examples
- `crm` — Pipedrive integration, scan, driver
- `chat` — Client chat, SellerAgent
- `auth` — Login, magic link, guards
- `livewire` — Livewire components
- `db` — Migrations, models
- `infra` — Sail, CI, config

### Examples
```
feat(crm): import custom fields from Pipedrive
fix(auth): prevent magic link enumeration
refactor(chat): extract message persistence to service
```
