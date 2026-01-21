# CLAUDE.md

Instructions for AI assistants working in this repository.

## Context

Central documentation repository for Gabriel's technology area. Docs-only (code in separate repos).

## Repository Structure

| Directory              | Function                                                      |
| ---------------------- | ------------------------------------------------------------- |
| `products/`            | Product documentation (business vision, roadmap)              |
| `tribes/`              | Organizational structure (tribes, squads, decisions)          |
| `building-directives/` | Engineering processes (handbook, discovery, design, delivery) |
| `people/`              | People management (onboarding, 1:1s, hiring)                  |
| `incidents/`           | Incident management (severity, postmortems)                   |
| `templates/`           | Reusable templates (ERD, PRD, product, squad)                 |

## Relationships

- **1 Tribe → N Products**: Borda Tribe owns 4 products, Digital Products owns 3
- **Squads operate assets**: App Gabriel Squad operates the mobile app repos

## Organizational Structure

- **Org**: ~40-60 people
- **Tribes**: Borda, Digital Products, Platform
- **Methodology**: Scrum/Kanban

## Decision Guidelines

### When making technical decisions:

1. **Document first** - Before implementing, document
2. **Consult stakeholders** - List who needs to be consulted
3. **Consider trade-offs** - Explain pros and cons
4. **Define success criteria** - How will we know if it worked?

### Decision levels:

| Level | Scope                   | Who decides               | Documentation           |
| ----- | ----------------------- | ------------------------- | ----------------------- |
| Squad | Local implementation    | Squad                     | Comment on Linear       |
| Tribe | Affects multiple squads | Engineering Manager + GPM | ERD + PRD or Directives |
| Org   | Affects multiple tribes | CPTO                      | Product Decision        |

### Principles:

- **Simplicity** - Prefer simple solutions
- **Reversibility** - Prefer reversible decisions
- **Data** - Base decisions on data when possible
- **Documentation** - If it is not documented, it does not exist

## Repo Conventions

- Documents in Portuguese
- Markdown for everything
- File names: lowercase with hyphens
- Templates in `templates/` for products and squads

## Integrations

- **Linear**: Project management
- **GitHub**: Code and PRs (assets discovered via org, not listed here)
- **DataDog**: Technical and product observability (analytics)
- **Slack**: Communication
- **n8n**: Automations
- **Notion**: Legacy docs (migrate here)

## Plan mode

- Make the plan extremely concise. Sacrifice grammar for the sake of conciseness.
- At the end of each plan, provide me with a list of unresolved questions I need to answer, if any.
