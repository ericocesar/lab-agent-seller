---
type: skill
name: security-audit
description: Security audit checklist
status: filled
---

# Security Audit

## Audit Checklist

- [ ] Auth guards: `auth:client` for clients, `auth` for companies
- [ ] Magic links: single-use, 15-min expiry, sha256 hashed
- [ ] Enumeration-safe: same response for matched/unmatched emails
- [ ] Encrypted storage: `encrypted` cast on `crm_connections.api_token`
- [ ] Email normalization: `Str::lower(trim())`, case-insensitive matching
- [ ] Session: `selected_company_id` validated against matched set
- [ ] CSRF: all routes behind web middleware
- [ ] Dependency: check for known vulnerabilities (`composer audit`)
- [ ] Environment: no secrets in `.env.example` or committed config
