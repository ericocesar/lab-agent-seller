---
type: doc
name: project-overview
description: High-level overview of the project, its purpose, and key components
category: overview
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Project Overview

## Purpose

Multi-tenant Laravel SaaS where a company connects its Pipedrive CRM, the system scans and imports the CRM graph locally, and each CRM contact (final client) logs in passwordlessly by magic link to chat with that company's PT-BR AI sales agent.

## Quick Facts

- Root: `/Users/ericocesar/Mac.local/boltdev/2026/lab-agent-seller`
- Languages: PHP ^8.3, Blade, JavaScript (Vite)
- Framework: Laravel 13, Livewire 4, TailwindCSS v4
- Entry: `public/index.php`, routes defined in `routes/web.php`
- Database: SQLite (local) / Postgres 18 (via Sail)

## Entry Points

| Entry | File |
|-------|------|
| Company login | `routes/web.php:login`, `app/Livewire/Auth/Login.php` |
| CRM connect | `app/Livewire/Crm/Connect.php` |
| Client access (magic link) | `app/Livewire/Client/Access.php` |
| Magic link verify | `app/Http/Controllers/Client/MagicLinkController.php` |
| Client chat | `app/Livewire/Client/Chat.php` |

## File Structure

```
app/
  Ai/Agents/       — SellerAgent (Laravel\Ai, OpenAI, streaming)
  Http/Controllers/ — MagicLinkController
  Jobs/            — ScanCrmConnection (ShouldQueue)
  Livewire/        — Auth, Client, Crm components
  Mail/            — MagicLinkMail
  Models/          — 17 Eloquent models + Concerns/IsLookup
  Services/        — ClientAccess, Crm drivers
bootstrap/         — Framework boot
config/            — Laravel config files
database/          — Migrations, factories, seeders
docs/agents/       — Agent-facing documentation
resources/views/   — Blade + Livewire views
routes/            — web.php, console.php
tests/             — Feature (20) + Unit, Pest
```

## Technology Stack

- **Backend**: Laravel 13, PHP 8.5 (Sail), Postgres 18, Redis
- **AI**: `laravel/ai` ^0.9 with OpenAI provider
- **Frontend**: Livewire 4, TailwindCSS v4, Blade, Vite
- **Testing**: Pest 4, PHPUnit 12, Mockery, Faker
- **Quality**: Laravel Pint (PSR-12/laravel), PHPStan level 7
- **Infra**: Laravel Sail (Docker), Mailpit, GitHub Actions CI

## Getting Started Checklist

1. Start services: `vendor/bin/sail up -d`
2. Install dependencies: `vendor/bin/sail composer install && vendor/bin/sail npm install`
3. Run migrations: `vendor/bin/sail artisan migrate`
4. Build frontend: `vendor/bin/sail npm run build`
5. Run tests: `vendor/bin/sail php artisan test --compact`

## Related Resources

- [Architecture](architecture.md)
- [Development Workflow](development-workflow.md)
- [Tooling](tooling.md)
