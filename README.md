# Personal Knowledge Base — AI-Powered External Brain

> An Obsidian vault with 19 specialized AI workers, 242 skills, and automated workflows built for a Business Analytics student targeting finance, consulting, and banking careers in the DACH region.

![Obsidian](https://img.shields.io/badge/Obsidian-vault-7C3AED?logo=obsidian&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-Code-orange?logo=anthropic&logoColor=white)
![Workers](https://img.shields.io/badge/AI_Workers-19-blue)
![Skills](https://img.shields.io/badge/Skills-242-green)

---

## Why I Built This

In an era where information moves faster than any individual can process it, the competitive edge belongs to those who connect the right dots at the right time — not those who work the hardest. Managing job applications, university coursework (M.Sc. Business Analytics, Uni Siegen), and continuous learning simultaneously demands a system that thinks alongside you, not one you have to maintain manually.

Most productivity systems fail because they add cognitive overhead instead of removing it. I wanted the opposite: an external brain that:
- Starts each session already knowing where I left off
- Has domain experts ready to review any work (finance, strategy, career, code)
- Never hallucinates financial data or outdated library versions
- Saves career decisions and financial insights automatically after each session

The result is a structured Obsidian vault wired to Claude Code with a team of 19 AI workers and 242 skills that can be invoked on demand.

---

## How It Works

### The Vault Structure

```
personal-kb/
├── 00 Home/          — Dashboard + Daily Notes (session start point)
├── 01 Me/            — Profile, Career tracker, Financial decisions
├── 02 Projects/      — Active projects with decision logs
├── 03 Knowledge/     — Zettelkasten-style knowledge notes
├── 04 Archive/       — Completed projects (event-driven only)
├── 05 Documents/     — Document index (files live in Google Drive)
├── 06 Ideas/         — Ideas + C-suite advisory pipeline
├── 07 Clients/       — Client projects with delivery workflow
├── workers/          — 19 AI worker profiles with methodology
└── skills/           — 242 installed skills catalog
```

### The Worker System

Each worker is a markdown file defining:
- **Role + Goal** — what they optimize for
- **Process** — step-by-step methodology (HOW to think, not just WHAT to do)
- **Quality Gates** — self-enforced checklist before delivering work
- **Uncertainty Protocol** — when to ask vs. when to act vs. when to stop
- **Tools + Skills** — which MCP tools and superpowers skills they use

Workers are orchestrated by a **Director** (Claude itself) using `superpowers:dispatching-parallel-agents` for parallel execution.

| Domain | Workers |
|--------|---------|
| Core (always in team) | QA Reviewer, Project Manager, Client Presenter |
| Finance & Analytics | Excel/Financial Modeler, Data Analyst, Broker, Treasury Expert |
| Research & Strategy | Research Agent, Strategy Consultant |
| Career | Career Specialist (CV/CL DE+EN, ATS, Interview Prep) |
| Engineering | Software Engineer, Debugger, Tester, Web Developer |
| Marketing | Marketer, Copywriter (Deutsch) |
| Security | Cybersecurity Expert |
| Meta | HR Agent (validates new workers before library entry) |
| Domain | Beverage Expert |

### The Skill System

242 skills installed from:
- **Superpowers** (anthropics/claude-plugins-official) — engineering workflows: TDD, systematic debugging, parallel agents, writing plans
- **alirezarezvani/claude-skills** (19.5k ⭐) — C-suite advisory, research, strategy, competitive intel
- **ComposioHQ/awesome-claude-skills** — business productivity tools
- **Custom** — `council` (philosophical filter before major decisions), `graphify` (knowledge graph analysis)

### Anti-Hallucination Protocol

All workers follow a strict rule: financial data, library versions, market statistics, and regulatory information must come from tools (WebSearch with date, context7 for docs), never from internal model knowledge. Unverified facts are tagged `[ASSUMPTION: verify currency]`.

### C-Suite Advisory Pipeline

When an idea passes the `council` philosophical filter:

```
council → [CFO + CMO + CTO + COO + Risk + CPO] parallel → cross-eval → artifact
```

Each C-level role uses a dedicated skill (`cfo-review`, `cmo-review`, etc.). For high-stakes decisions (>6 months commitment or significant capital), `cross-eval` runs a multi-model consensus check.

### Self-Client Mode

When I consult my own financial or career workers, insights are automatically saved:
- Financial decisions → `01 Me/Finance.md`
- Career decisions → `01 Me/Career.md`

This turns every working session into a contribution to my personal knowledge base.

---

## Session Start (ADHD-Optimized)

Every session auto-reads Dashboard + Gmail MCP + Career.md and surfaces:

```
Here's what's up:
- [N] emails need a response
- Active projects: [N], nearest deadline: [what/when]
- [N] pending tasks

Where do we start?
[ Process email ] [ Work on [project] ] [ Full update ] [ Other ]
```

No manual triggers. No setup. The system orients itself.

---

## Tech Stack

| Layer | Tool |
|-------|------|
| Knowledge base | Obsidian |
| AI backbone | Claude Code (claude-sonnet-4-6) |
| Email integration | Gmail MCP |
| Document processing | markitdown-mcp (PDF, Word, Excel) |
| Library docs | context7 MCP (always-current documentation) |
| GitHub integration | @modelcontextprotocol/server-github |
| File storage | Google Drive MCP |
| Calendar | Google Calendar MCP |
| Skills runtime | Superpowers plugin (Anthropic official) |

---

## Example Prompts

**Career workflow:**
```
разбери мою заявку в [компания] на позицию [должность]
→ Career Specialist (WRK-012) reads JD via WebSearch,
  audits CV for ATS keywords, rewrites cover letter,
  saves decision to Career.md
```

**Idea evaluation:**
```
обдумай идею: B2B SaaS for compliance automation in DACH
→ council filter → 6 C-suite agents in parallel
  → CFO checks unit economics, CTO checks build complexity,
  CMO checks market, GC checks regulatory risk
  → synthesis with recommendation
```

**Research:**
```
dossier: [компания] перед интервью завтра
→ Research Agent (WRK-010) uses dossier skill:
  recent news, financials, culture, likely interview questions
  → saved as interview prep note
```

**Knowledge capture:**
```
[attaches lecture PDF]
→ markitdown-mcp extracts content
→ knowledge note created in 03 Knowledge/
→ linked to relevant project or topic
```

---

## Repository Structure

This repo is the **English translation** of my local Russian vault. The vault is designed to work with [Claude Code](https://claude.ai/code) — the `CLAUDE.md` files at each level provide context-aware instructions that Claude reads automatically.

To adapt this for your own use:
1. Clone the repo into your Obsidian vault folder
2. Install Claude Code
3. Install Superpowers plugin: `claude plugin install superpowers@claude-plugins-official`
4. Configure MCP servers (see `CLAUDE.md` for the full settings)
5. Start a session from the vault root — Claude reads `CLAUDE.md` automatically

---

## Status

Active development. Using this daily for:
- Werkstudent job search in DACH (finance/consulting/banking)
- M.Sc. Business Analytics coursework at Uni Siegen
- Client project delivery (freelance work)

---

*Built with [Claude Code](https://claude.ai/code) — Obsidian as the UI, Claude as the engine.*
