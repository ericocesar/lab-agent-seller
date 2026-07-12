---
type: agent
name: frontend-specialist
description: Frontend specialist for Livewire + Blade + TailwindCSS
status: filled
---

# Frontend Specialist

## Responsibilities

Build and maintain Livewire components, Blade views, TailwindCSS styling, and Vite asset pipeline.

## Relevant Files

| Layer | Path |
|-------|------|
| Livewire components | `app/Livewire/Auth/`, `app/Livewire/Client/`, `app/Livewire/Crm/` |
| Blade views | `resources/views/livewire/`, `resources/views/components/`, `resources/views/layouts/` |
| CSS | `resources/css/` |
| JS | `resources/js/` |

## Key Conventions

- TailwindCSS v4 for styling
- Livewire 4 with Alpine.js for interactivity
- PT-BR for all user-facing text
- State kept server-side; validate in actions
- Named routes and `route()` for links

## Build

```sh
vendor/bin/sail npm run build    # production
vendor/bin/sail npm run dev      # dev server
```
