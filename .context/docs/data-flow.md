---
type: doc
name: data-flow
description: How data moves through the system and external integrations
category: data-flow
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Data Flow & Integrations

## High-level Flow

### CRM Scan Flow
```
Company → Connect::connect → validateToken (Pipedrive API)
  → CrmConnection upserted → ScanCrmConnection enqueued
  → Scan imports: pipelines → stages → customFields → persons → deals
  → All upserted by external_id per crm_connection_id
  → Status: pending → running → success|failed
```

### Client Chat Flow
```
Client submits email → MagicLinkService::matchedCompanies
  → Magic link emailed (15min, single-use)
  → Link verified → Client upserted → Logged in (client guard)
  → Chat::sendMessage → persist user turn
  → SellerAgent::stream (OpenAI via laravel/ai)
  → Persist assistant turn → activity panel updated
```

## Module Dependencies

- **Livewire components** → `app/Services/`
- **ScanCrmConnection** → `CrmDriverManager` → `PipedriveDriver`
- **SellerAgent** → `laravel/ai` (OpenAI)
- **Chat** → `SellerAgent`, `Conversation`/`Message` models
- **Access** → `MagicLinkService`
- **Connect** → `CrmDriverManager`, `CrmConnection`

## Service Layer

| Service | File |
|---------|------|
| MagicLinkService | `app/Services/ClientAccess/MagicLinkService.php` |
| CrmDriverManager | `app/Services/Crm/CrmDriverManager.php` |
| PipedriveDriver | `app/Services/Crm/Drivers/PipedriveDriver.php` |

## External Integrations

| System | Authentication | Client |
|--------|---------------|--------|
| Pipedrive REST v1 | Personal API token (query param) | `PipedriveDriver` via `Http::facade` |
| OpenAI | API key via env | `SellerAgent` via `laravel/ai` |
| SMTP/Mailpit | SMTP config | `MagicLinkMail` via `Mail::facade` |

## Related Resources

- [Architecture](architecture.md)
