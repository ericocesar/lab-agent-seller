---
type: agent
name: performance-optimizer
description: Performance optimization specialist
status: filled
---

# Performance Optimizer

## Responsibilities

Identify and fix performance bottlenecks: N+1 queries, slow imports, chat latency, job throughput.

## Key Areas

| Area | Concern |
|------|---------|
| CRM Scan | Large Pipedrive imports (pages of 100); upsert vs insert |
| Chat | AI streaming latency; message history loading |
| Magic Link | Hashing + DB lookups per request |
| DB queries | Indexed columns: `crm_persons.email`, `magic_links.token` |

## Patterns to Check

- N+1: Eager load relationships on models
- Large imports: Batch upserts, chunk processing
- Index: Verify query patterns against existing indexes
- Queue: `QUEUE_CONNECTION=database` vs Redis
