---
type: doc
name: tooling
description: Scripts, IDE settings, automation, and developer productivity tips
category: tooling
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Tooling & Productivity Guide

## Required Tooling

| Tool | Version | Purpose |
|------|---------|---------|
| Docker + Docker Compose | Latest | Laravel Sail runtime |
| PHP | ^8.3 | Application runtime (8.5 in Sail) |
| Composer | Latest | PHP dependency management |
| Node.js | ^20 | Frontend asset building |

## Automation

- **Laravel Pint**: `vendor/bin/sail bin pint --dirty --format agent` — auto-format PHP after every change
- **PHPStan**: `vendor/bin/sail composer types:check` — static analysis level 7
- **Pest**: `vendor/bin/sail php artisan test --compact` — test suite
- **Full quality gate**: `vendor/bin/sail composer test` runs lint → types → tests
- **MCP**: Laravel Boost MCP server configured in `.mcp.json`

## IDE Setup

- EditorConfig (`.editorconfig`) for consistent formatting
- Laravel Pint + PHPStan integration recommended

## Productivity Tips

- Use `vendor/bin/sail artisan make: --no-interaction` for scaffolding
- Inspect routes: `vendor/bin/sail artisan route:list`
- Read config: `vendor/bin/sail artisan config:show <key>`
- View mail: Mailpit inbox (available when Sail is running)
- Check `AGENTS.md` for full command reference and conventions

## Related Resources

- [Development Workflow](development-workflow.md)
