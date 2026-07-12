---
type: doc
name: architecture
description: System architecture, layers, patterns, and design decisions
category: architecture
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Architecture Notes

## System Architecture Overview

Layered Laravel 13 monolith: HTTP/Livewire presentation → service layer (`app/Services`) → Eloquent persistence, with a provider-agnostic driver abstraction for CRM integration and queued jobs for background scanning. Runs inside Docker via Laravel Sail.

## Architectural Layers

- **Presentation**: Livewire components (`app/Livewire/`) + Blade views (`resources/views/`) + one traditional controller (`MagicLinkController`)
- **Service Layer**: `app/Services/ClientAccess/MagicLinkService`, `app/Services/Crm/` (driver manager, contracts, drivers, exceptions)
- **AI Agent**: `app/Ai/Agents/SellerAgent` — `laravel/ai` agent with OpenAI provider, streamed responses
- **Background Jobs**: `app/Jobs/ScanCrmConnection` — scan state machine, upsert by external_id
- **Persistence**: Eloquent models (`app/Models/`), 16 app tables + 3 framework tables

## Entry Points

| Entry | File |
|-------|------|
| Company login | `routes/web.php` → `App\Livewire\Auth\Login` |
| CRM connect | `routes/web.php` → `App\Livewire\Crm\Connect` |
| Client access | `routes/web.php` → `App\Livewire\Client\Access` |
| Magic link verify | `routes/web.php` → `App\Http\Controllers\Client\MagicLinkController::verify` |
| Client chat | `routes/web.php` → `App\Livewire\Client\Chat` |

## Top Directories

```
app/           — 40 files (controllers, jobs, livewire, mail, models, services, ai)
config/        — 10 files (app, auth, cache, database, filesystems, logging, mail, queue, services, session)
database/      — 29 files (19 migrations, factories, seeders)
resources/     — 25 files (views, CSS, JS)
routes/        — 2 files (web.php, console.php)
tests/         — 23 files (Feature 20, Unit, TestCase, Pest.php)
```

## Related Resources

- [Project Overview](project-overview.md)
- [Data Flow](data-flow.md)
