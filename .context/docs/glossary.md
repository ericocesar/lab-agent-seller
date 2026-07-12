---
type: doc
name: glossary
description: Project terminology, type definitions, domain entities, and business rules
category: glossary
generated: 2026-07-11
status: filled
scaffoldVersion: "2.0.0"
---

# Glossary & Domain Concepts

## Core Terms

| Term | Definition | Code Location |
|------|-----------|---------------|
| Company (tenant) | `users` row; owns one CRM connection | `app/Models/User.php` |
| Final client | `clients` row; logs in via magic link | `app/Models/Client.php` |
| CrmConnection | Company's Pipedrive connection (one per company) | `app/Models/CrmConnection.php` |
| CrmScan | Record of a CRM import attempt | `app/Models/CrmScan.php` |
| Pipeline | Sales pipeline from Pipedrive | `app/Models/Pipeline.php` |
| PipelineStage | Stage within a pipeline | `app/Models/PipelineStage.php` |
| CrmPerson | Contact/person from Pipedrive | `app/Models/CrmPerson.php` |
| Deal | Deal/opportunity from Pipedrive | `app/Models/Deal.php` |
| CustomField | Custom field definition from Pipedrive | `app/Models/CustomField.php` |
| MagicLink | Single-use, 15-min passwordless login | `app/Models/MagicLink.php` |
| Conversation | One per (client, company) pair | `app/Models/Conversation.php` |
| Message | Turn in a conversation (user or assistant) | `app/Models/Message.php` |
| SellerAgent | PT-BR AI sales agent per company | `app/Ai/Agents/SellerAgent.php` |

## Enumerations

| Enum | Type | Values | Location |
|------|------|--------|----------|
| ScanStatus | DB lookup (IsLookup) | pending, running, success, failed | `app/Models/ScanStatus.php` |
| MessageRole | DB lookup (IsLookup) | user, assistant | `app/Models/MessageRole.php` |
| DealStatus | DB lookup (IsLookup) | open, won, lost | `app/Models/DealStatus.php` |
| CrmTokenStatus | PHP Enum | Valid, Invalid, Retryable | `app/Services/Crm/CrmTokenStatus.php` |

## Acronyms

| Acronym | Expansion |
|---------|-----------|
| CRM | Customer Relationship Management |
| PT-BR | Portuguese (Brazil) |
| SaaS | Software as a Service |
| MCP | Model Context Protocol |

## Personas

- **Company user (tenant)**: Authenticates, connects CRM, monitors scan status
- **Final client**: Logs via magic link, chats with AI agent about commercial relationship

## Domain Rules

- Magic links are single-use, 15-min expiry, enumeration-safe (same response shown regardless of match)
- CRM scans are idempotent (upsert by external_id); partial failures keep imported data (no rollback)
- One conversation per (client, company) pair enforced by DB unique constraint
- `SellerAgent` has no CRM/tool access in MVP — answers only from conversation history

## Related Resources

- [Project Overview](project-overview.md)
