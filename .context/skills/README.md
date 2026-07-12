# Skills

On-demand expertise for AI agents. Skills are task-specific procedures that get activated when relevant.

> Project: lab-agent-seller

## How Skills Work

1. **Discovery**: AI agents discover available skills
2. **Matching**: When a task matches a skill's description, it's activated
3. **Execution**: The skill's instructions guide the AI's behavior

## Available Skills

### Built-in Skills

| Skill | Description | Phases |
|-------|-------------|--------|
| [Commit Message](./commit-message/SKILL.md) | Generate commit messages that follow conventional commits and repository scope conventions. Use when Creating git commits after code changes, Writing commit messages for staged changes, or Following conventional commit format for the project | E, C |
| [Pr Review](./pr-review/SKILL.md) | Review pull requests against team standards and best practices. Use when Reviewing a pull request before merge, Providing feedback on proposed changes, or Validating PR meets project standards | R, V |
| [Code Review](./code-review/SKILL.md) | Review code quality, patterns, and best practices. Use when Reviewing code changes for quality, Checking adherence to coding standards, or Identifying potential bugs or issues | R, V |
| [Test Generation](./test-generation/SKILL.md) | Generate comprehensive test cases for code. Use when Writing tests for new functionality, Adding tests for bug fixes (regression tests), or Improving test coverage for existing code | E, V |
| [Documentation](./documentation/SKILL.md) | Generate and update technical documentation. Use when Documenting new features or APIs, Updating docs for code changes, or Creating README or getting started guides | P, C |
| [Refactoring](./refactoring/SKILL.md) | Refactor code safely with a step-by-step approach. Use when Improving code structure without changing behavior, Reducing code duplication, or Simplifying complex logic | E |
| [Bug Investigation](./bug-investigation/SKILL.md) | Investigate bugs systematically and perform root cause analysis. Use when Investigating reported bugs, Diagnosing unexpected behavior, or Finding the root cause of issues | E, V |
| [Feature Breakdown](./feature-breakdown/SKILL.md) | Break down features into implementable tasks. Use when Planning new feature implementation, Breaking large tasks into smaller pieces, or Creating implementation roadmap | P |
| [Api Design](./api-design/SKILL.md) | Design RESTful APIs following best practices. Use when Designing new API endpoints, Restructuring existing APIs, or Planning API versioning strategy | P, R |
| [Security Audit](./security-audit/SKILL.md) | Review code and infrastructure for security weaknesses. Use when Reviewing code for security vulnerabilities, Assessing authentication/authorization, or Checking for OWASP top 10 issues | R, V |
| [dotcontext-workflow](./dotcontext-workflow/SKILL.md) | Operate PREVC workflow through any adapter (MCP, CLI, hooks, Pi) | P, R, E, V, C |
| [dotcontext-tooling](./dotcontext-tooling/SKILL.md) | When to use harness actions (init, guide, advance, manage, sensors) across any adapter | P, R, E, V, C |
| [dotcontext-workflow-p](./dotcontext-workflow-p/SKILL.md) | PREVC phase P (Planning) checklist for harness-backed work | P |
| [dotcontext-workflow-r](./dotcontext-workflow-r/SKILL.md) | PREVC phase R (Review) checklist for harness-backed work | R |
| [dotcontext-workflow-e](./dotcontext-workflow-e/SKILL.md) | PREVC phase E (Execution) checklist for harness-backed work | E |
| [dotcontext-workflow-v](./dotcontext-workflow-v/SKILL.md) | PREVC phase V (Validation) checklist for harness-backed work | V |
| [dotcontext-workflow-c](./dotcontext-workflow-c/SKILL.md) | PREVC phase C (Confirmation) checklist for harness-backed work | C |

### Custom Skills

| Skill | Description | Phases |
|-------|-------------|--------|
| [ai-sdk-development](./ai-sdk-development/SKILL.md) | TRIGGER when working with ai-sdk which is Laravel official first-party AI SDK. Activate when building, editing AI agents, chatbots, text generation, image generation, audio/TTS, transcription/STT, embeddings, RAG, vector stores, reranking, structured output, streaming, conversation memory, tools, queueing, broadcasting, and provider failover across OpenAI, Anthropic, Gemini, Azure, Groq, xAI, DeepSeek, Mistral, Ollama, ElevenLabs, Cohere, Jina, and VoyageAI. Invoke when the user references ai-sdk, the `Laravel\Ai\` namespace, or this project's AI features — not for other AI packages used directly. | - |
| [blaze-optimize](./blaze-optimize/SKILL.md) | Set up and optimize Blade component rendering with Blaze. Use when installing Blaze, optimizing components, or configuring @blaze directives and strategies. | - |
| [laravel-best-practices](./laravel-best-practices/SKILL.md) | Apply this skill whenever writing, reviewing, or refactoring Laravel PHP code. This includes creating or modifying controllers, models, migrations, form requests, policies, jobs, scheduled commands, service classes, and Eloquent queries. Triggers for N+1 and query performance issues, caching strategies, authorization and security patterns, validation, error handling, queue and job configuration, route definitions, and architectural decisions. Also use for Laravel code reviews and refactoring existing Laravel code to follow best practices. Covers any task involving Laravel backend PHP code patterns. | - |
| [livewire-development](./livewire-development/SKILL.md) | Use for any task or question involving Livewire. Activate if user mentions Livewire, wire: directives, or Livewire-specific concepts like wire:model, wire:click, wire:sort, or islands, invoke this skill. Covers building new components, debugging reactivity issues, real-time form validation, drag-and-drop, loading states, migrating from Livewire 3 to 4, converting component formats (SFC/MFC/class-based), and performance optimization. Do not use for non-Livewire reactive UI (React, Vue, Alpine-only, Inertia.js) or standard Laravel forms without Livewire. | - |
| [pest-testing](./pest-testing/SKILL.md) | Use this skill for Pest PHP testing in Laravel projects only. Trigger whenever any test is being written, edited, fixed, or refactored — including fixing tests that broke after a code change, adding assertions, converting PHPUnit to Pest, adding datasets, and TDD workflows. Always activate when the user asks how to write something in Pest, mentions test files or directories (tests/Feature, tests/Unit, tests/Browser), or needs browser testing, smoke testing multiple pages for JS errors, or architecture tests. Covers: test()/it()/expect() syntax, datasets, mocking, browser testing (visit/click/fill), smoke testing, arch(), Livewire component tests, RefreshDatabase, and all Pest 4 features. Do not use for factories, seeders, migrations, controllers, models, or non-test PHP code. | - |
| [tailwindcss-development](./tailwindcss-development/SKILL.md) | Always invoke when the user's message includes 'tailwind' in any form. Also invoke for: building responsive grid layouts (multi-column card grids, product grids), flex/grid page structures (dashboards with sidebars, fixed topbars, mobile-toggle navs), styling UI components (cards, tables, navbars, pricing sections, forms, inputs, badges), adding dark mode variants, fixing spacing or typography, and Tailwind v3/v4 work. The core use case: writing or fixing Tailwind utility classes in HTML templates (Blade, JSX, Vue). Skip for backend PHP logic, database queries, API routes, JavaScript with no HTML/CSS component, CSS file audits, build tool configuration, and vanilla CSS. | - |

## Creating Custom Skills

Create a new skill by adding a directory with a `SKILL.md` file:

```
.context/skills/
└── my-skill/
    ├── SKILL.md          # Required: source skill definition
    ├── scripts/          # Optional: deterministic helpers
    ├── references/       # Optional: load-on-demand details
    └── assets/           # Optional: output resources
```

### Skill Anatomy

```md
The source file under `.context/skills/` keeps internal scaffold metadata so dotcontext can track fill status.
When exported to AI-tool skill directories, the portable frontmatter should keep only:

---
name: my-skill
description: Describe what the skill does and the concrete triggers for when to use it
---

## Workflow
1. Step one
2. Step two

## Examples
```
[Short example]
```

## Quality Bar
- List the checks and constraints that keep the skill reliable

## Resource Strategy
- Explain when to add `scripts/`, `references/`, or `assets/`
```

Keep activation language in the description frontmatter, keep the body concise, and avoid extra docs such as `README.md` or `CHANGELOG.md` inside the skill folder.

## PREVC Phase Mapping

| Phase | Name | Skills |
|-------|------|--------|
| P | Planning | feature-breakdown, documentation, api-design |
| R | Review | pr-review, code-review, api-design, security-audit |
| E | Execution | commit-message, test-generation, refactoring, bug-investigation |
| V | Validation | pr-review, code-review, test-generation, security-audit |
| C | Confirmation | commit-message, documentation |
