---
type: skill
name: feature-breakdown
description: Feature breakdown into tasks
status: filled
---

# Feature Breakdown

## Template

### Feature: [Name]

1. **Database** — migrations, model changes, seeders
2. **Service Layer** — new services or modifications
3. **Livewire Component** — new or updated component
4. **Views** — Blade templates
5. **Routes** — route definitions
6. **Tests** — Pest feature tests

### Example: Add new CRM provider
1. Create `CrmDriver` implementation in `app/Services/Crm/Drivers/`
2. Register in `CrmDriverManager`
3. Add provider slug to `crm_providers` seeder
4. Write driver tests with `Http::fake()`
5. Test full scan flow
