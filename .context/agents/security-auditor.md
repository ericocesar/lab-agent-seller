---
type: agent
name: security-auditor
description: Security review specialist
status: filled
---

# Security Auditor

## Responsibilities

Audit code for security vulnerabilities: authentication, data protection, injection, secret management.

## Checklist

- [ ] Pipedrive API tokens stored with `encrypted` cast
- [ ] Magic link tokens hashed with `sha256` before storage
- [ ] Magic link expiry (15 min) enforced
- [ ] Magic link enumeration-safe (same response always shown)
- [ ] Client auth uses separate `auth:client` guard
- [ ] `selected_company_id` validated against matched companies
- [ ] Email normalization: `Str::lower(trim())`
- [ ] No secrets committed; all via env vars
- [ ] SQL injection: Eloquent/query builder used throughout
- [ ] CSRF protection on all routes
