---
type: agent
name: architect-specialist
description: System architecture and design decisions
status: filled
---

# Architect Specialist

## Responsibilities

Design and review system architecture: layer boundaries, service contracts, driver patterns, data flow.

## Relevant Files

| Layer | Path |
|-------|------|
| Services | `app/Services/Crm/` (driver pattern) |
| AI Agents | `app/Ai/Agents/SellerAgent.php` |
| Jobs | `app/Jobs/ScanCrmConnection.php` |
| Docs | `docs/agents/architecture.md` |

## Architecture Decisions

- **Layered monolith**: Livewire → Services → Eloquent
- **Driver pattern**: `CrmDriver` interface + `CrmDriverManager` registry for CRM providers
- **Queued import**: `ScanCrmConnection` (ShouldQueue) for async CRM scanning
- **AI streaming**: `laravel/ai` streaming via SSE events (`TextDelta`)
- **No rollback on scan failure**: partial imports preserved
- **Single conversation per (client, company)**: unique constraint

## Quality Checks

- Validate layer boundaries (no service calling Livewire)
- Ensure driver interface is provider-agnostic
- Confirm idempotent imports by `external_id`
