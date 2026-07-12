---
type: skill
name: api-design
description: RESTful API and route design
status: filled
---

# API Design

## Routes

All routes in `routes/web.php`. This project uses Livewire for most interactions; only `MagicLinkController::verify` is a traditional HTTP endpoint.

| Method | URI | Action |
|--------|-----|--------|
| GET | `/crm/connect` | `Livewire\Crm\Connect` |
| GET | `/acesso` | `Livewire\Client\Access` |
| GET | `/acesso/{token}` | `MagicLinkController@verify` |
| GET | `/selecionar-empresa` | `Livewire\Client\CompanySelection` |
| GET | `/chat` | `Livewire\Client\Chat` |
| GET | `/logout` | Logout |
| GET | `/login` | `Livewire\Auth\Login` |
