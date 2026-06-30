---
type: index
hub: skills
date: 2026-06-30
---

# Skills Library

Catalog of all installed skills (`~/.claude/skills/`).
Skills are invoked via the Skill tool or `/skill-name` in Claude Code.

Sources:
- Superpowers (anthropics/claude-plugins-official) -- engineering workflow
- alirezarezvani/claude-skills (19.5k stars) -- C-suite, research, strategy
- ComposioHQ/awesome-claude-skills (curated) -- productivity, business tools
- Custom (~/.claude/skills/council, graphify)

---

## C-Suite Advisory

For the idea pipeline (06 Ideas/CLAUDE.md) and strategic decisions.

| Skill | Purpose | Worker |
|-------|---------|--------|
| `cfo-advisor` | CFO as strategist: burn rate, fundraising, unit economics | WRK-005, WRK-018 |
| `cfo-review` | Financial review of a plan/idea (/cs:cfo-review) | C-suite pipeline |
| `cmo-advisor` | CMO as strategist: brand, growth model, channels | WRK-016 |
| `cmo-review` | Marketing review of a plan/idea | C-suite pipeline |
| `cto-advisor` | CTO as strategist: tech debt, architecture, team | WRK-013 |
| `cto-review` | Technical review of a plan/idea | C-suite pipeline |
| `coo-advisor` | COO: operations, OKR, scaling playbooks | WRK-002 |
| `cpo-advisor` | CPO: product vision, PMF, portfolio strategy | |
| `cpo-review` | Product review of a plan/idea | C-suite pipeline |
| `cro-advisor` | CRO: revenue model, NRR, sales scaling | |
| `cro-review` | Revenue review of a plan/idea | C-suite pipeline |
| `ciso-advisor` | CISO: security strategy, compliance, incident response | |
| `gc-review` | Legal and regulatory review (General Counsel) | C-suite pipeline |
| `cross-eval` | Multi-model consensus for high-stakes decisions | C-suite pipeline |
| `decide` | Logging the final decision to memory | After C-suite |
| `scenario-war-room` | Scenario stress-test before a key decision | |
| `competitive-intel` | Systematic competitor research | WRK-016 |

---

## Research

For Research Agent (WRK-010, research-agent.md) and any research tasks.

| Skill | Purpose |
|-------|---------|
| `research` | Router: determines the request type -> delegates to a specialist |
| `pulse` | What people are saying on a topic right now (Reddit/HN/web, last 30 days) |
| `dossier` | Due diligence / prep for a meeting with a company or person |
| `litreview` | Academic literature review |
| `market-research` | TAM/SAM/SOM, segmentation, sizing methodology |
| `lead-research-assistant` | Finding leads and contacts for B2B |
| `competitive-teardown` | Deep dive on a competitor (features, pricing, SEO, reviews) |
| `competitive-ads-extractor` | Extracting competitor ad materials |

---

## Strategy & Product

| Skill | Purpose | Worker |
|-------|---------|--------|
| `product-strategist` | OKR cascade, quarterly planning, competitive landscape | WRK-011 |
| `senior-pm` | PM toolkit: planning, stakeholders, delivery | WRK-002 |
| `meeting-insights-analyzer` | Analyzing meeting transcripts, communication patterns | WRK-002 |

---

## Business Tools

| Skill | Purpose | Worker |
|-------|---------|--------|
| `tailored-resume-generator` | Generating a resume tailored to a specific job posting | WRK-012 |
| `content-research-writer` | Content with research and citations | WRK-007, WRK-016 |
| `webapp-testing` | Web application testing | WRK-015 |
| `mcp-builder` | Building MCP servers for new integrations | WRK-013 |
| `alpha-vantage-automation` | Financial data: quotes, fundamentals | WRK-009, WRK-018 |

---

## Engineering Workflow (Superpowers)

| Skill | Purpose | Worker |
|-------|---------|--------|
| `superpowers:brainstorming` | Designing a solution before coding | |
| `superpowers:writing-plans` | Creating an implementation plan | WRK-013, WRK-017 |
| `superpowers:executing-plans` | Executing a plan step by step | |
| `superpowers:systematic-debugging` | Structured bug investigation | WRK-014 |
| `superpowers:test-driven-development` | TDD methodology | WRK-015 |
| `superpowers:finishing-a-development-branch` | Final code checks before delivery | WRK-013, WRK-017 |
| `superpowers:requesting-code-review` | Requesting a review | WRK-013, WRK-017 |
| `superpowers:receiving-code-review` | Processing review feedback | WRK-013 |
| `superpowers:verification-before-completion` | Final deliverable verification | All workers |
| `superpowers:dispatching-parallel-agents` | Parallel orchestration | |
| `superpowers:subagent-driven-development` | Complex tasks with sub-tasks | |

---

## Vault-Specific (Custom)

| Skill | Purpose |
|-------|---------|
| `council` | Philosophical idea filter (before C-suite pipeline) |
| `graphify` | Analyzing the vault as a knowledge graph, finding connections |

---

## Adding a New Skill

1. Find in alirezarezvani/claude-skills or ComposioHQ/awesome-claude-skills
2. Verify safety: no prompt injection, no data exfiltration
3. Copy to `~/.claude/skills/skill-name/`
4. Add to this table with a description and worker mapping
5. Update workers/CLAUDE.md Master Skills Mapping if needed

Next available worker ID: WRK-019
