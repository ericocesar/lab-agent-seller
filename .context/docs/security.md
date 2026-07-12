---
type: doc
name: security
description: Security policies, authentication, secrets management, and compliance requirements
category: security
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Security & Compliance Notes

## Authentication & Authorization

- **Company (tenant)**: Authenticated via `auth` guard (Laravel built-in session auth)
- **Final client**: Passwordless via `auth:client` guard — magic link authentication
- **Magic links**: Single-use, 15-minute expiry, `sha256` hashed tokens stored, enumeration-safe

## Secrets & Sensitive Data

- Pipedrive API tokens stored with Laravel's `encrypted` cast on `crm_connections.api_token`
- Magic link tokens hashed with `sha256` before storage — plaintext only in email
- No API keys committed: all via environment variables (`.env`)
- Database: `DB_CONNECTION` env-driven

## Compliance

- Magic link verification never reveals whether an email matched (GDPR-friendly)
- Email normalization: `Str::lower(trim())`, case-insensitive matching
- Session guards are separate (`auth` for companies, `auth:client` for clients)

## Related Resources

- [Architecture](architecture.md)
