# Personal KB — Master Instructions

This vault is an external brain, career tracker, and knowledge management system.
Owner: M.Sc. Business Analytics student (Uni Siegen), targeting finance/consulting/banking.
ADHD-optimized: the system runs automatically. Minimal manual effort required.

## Vault Structure

```
~/projects/personal-kb/
├── 00 Home/          — Dashboard and Daily Notes
├── 01 Me/            — profile, career, goals, finances
├── 02 Projects/      — active projects
├── 03 Knowledge/     — studies and knowledge (Zettelkasten)
├── 04 Archive/       — closed projects (event-driven only)
├── 05 Documents/     — document index (files live in Google Drive)
├── 06 Ideas/         — ideas, creativity, someday
├── 07 Clients/       — client projects (see 07 Clients/CLAUDE.md)
├── skills/           — installed skills catalog (skills/README.md)
├── workers/          — worker library (workers/README.md)
└── templates/        — templates for all note types
```

## Session Start Behavior (AUTOMATIC)

When opening a new session from this folder:
1. Read `00 Home/Dashboard.md`
2. Check Gmail MCP: unread and starred emails
3. Read `01 Me/Career.md` if job search status is active
4. Output a brief summary and offer action options

Summary format:
```
Here's what's up:
- [N] emails need a response
- Active projects: [N], nearest deadline: [what/when]
- [if pending tasks: N tasks pending]

Where do we start?
[ Process email ] [ Work on [project] ] [ Full update ] [ Other ]
```

### What "Full Update" Does

1. Read Dashboard.md (flat list of active projects)
2. Read 01 Me/Career.md (job search status if active)
3. Gmail MCP: unread + starred (up to 10 most recent)
4. Synthesize: what's urgent, what's pending, what can be closed
5. Create/update today's Daily Note in 00 Home/Daily Notes/
6. Output summary: projects + email + recommended next action
7. Do NOT take any action automatically — only show the picture and wait for a command

## Automatic Behavior (without user commands)

### File attached to message
- Always process via markitdown-mcp
- Determine content type and place in the appropriate hub
- If the message includes a prompt: execute the prompt AND save to vault
- 3+ files: launch parallel agents (one per file)

### Message type is determined automatically
- Vision / desire / "I want to try" / "it would be cool" → fleeting note in 06 Ideas/fleeting/
- Finalized project decision → decision note in the relevant 02 Projects/[project]/
- Something learned or explained → knowledge note in 03 Knowledge/
- Project status update → status note in 02 Projects/[project]/
- Email or task requiring action → task card in 00 Home/

### "Close / finish / switch to another project"
Always clarify: "Switch to another project or archive this one?"
Archiving only after explicit confirmation.

### "Save progress"
1. Update the current project file
2. Create/update a note in the appropriate hub (type determined automatically)
3. Report what was saved

## Frontmatter Schema (required for all notes)

```yaml
---
type: decision | knowledge | status | daily | task | document | idea | profile | career | goals | dashboard | index
project: werkstudent | studium | personal | [name]
hub: home | me | projects | knowledge | archive | documents | ideas | workers | skills | clients
topic: finance | math | career | optimization | tech | legal | [topic]
status: active | pending | completed | archived
date: YYYY-MM-DD
---
```

## Archiving Rules

- 03 Knowledge/: NEVER automatically — knowledge doesn't expire
- Decisions and conclusions: NEVER — this is the history of thinking
- 02 Projects/[project]/: only on command + explicit user confirmation
- Daily Notes: after 30 days, provided at least one of the following was extracted: a knowledge note, a decision, or a transferred task
- 05 Documents/: when replaced by a new version

## Skills Awareness

Use existing skills instead of reinventing the wheel.
Don't work around a skill when one exists. Offer to confirm with the user if needed.

| Skill | When to use |
|-------|------------|
| council | "think through idea: [X]" — philosophical filter before C-suite |
| superpowers:dispatching-parallel-agents | any orchestration pattern with 2+ independent tasks |
| superpowers:brainstorming | designing new systems or features |
| superpowers:systematic-debugging | something broken in vault or workflow |
| superpowers:writing-plans | after brainstorming, before implementation |
| superpowers:test-driven-development | writing code with tests |
| superpowers:verification-before-completion | final check on any deliverable |
| graphify | analyze vault as knowledge graph, find connections |
| research | any research request — router to specialized skills |
| pulse | what's happening with a topic now (Reddit/HN/web last 30 days) |
| dossier | meeting prep / due diligence on a company or person |
| litreview | academic literature review |
| market-research | TAM/SAM/SOM, market segmentation, methodology |
| competitive-intel | systematic competitor research |
| competitive-teardown | deep dive on a specific competitor |
| product-strategist | OKR, product vision, roadmap |
| senior-pm | project management, planning |
| cfo-review | financial expert review of idea/plan |
| cmo-review | marketing expert review of idea/plan |
| cto-review | technical expert review of idea/plan |
| cpo-review | product expert review of idea/plan |
| cro-review | revenue model expert review |
| gc-review | legal and regulatory expert review |
| cross-eval | multi-model consensus for high-stakes decisions |
| cfo-advisor | CFO as advisor (not reviewer — strategist) |
| cmo-advisor | CMO advisor |
| cto-advisor | CTO advisor |
| coo-advisor | COO operations advisor |
| cpo-advisor | CPO product advisor |
| cro-advisor | CRO revenue advisor |
| ciso-advisor | security and compliance advisor |
| scenario-war-room | scenario stress-test before making a decision |

## Orchestration Patterns

### "think through idea: [X]" — Council filter
1. Invoke `council` skill with the idea
2. Three possible outcomes:
   - Green: proceed to "analyze idea"
   - "What if...": Council proposes improvement, idea re-enters loop (max 3 iterations)
   - Hard no: archive with explanation
3. Iteration loop: pass what changed, NOT the previous verdict (except on 3rd iteration)

### "analyze idea: [X]" — C-suite pipeline
Only after a positive Council verdict.
Details: see 06 Ideas/CLAUDE.md

### "cleanup"
In parallel via superpowers:dispatching-parallel-agents:
- Agent 1: Daily Notes older than 30 days → extract insights → archive
- Agent 2: Projects with status completed → Archive
- Agent 3: duplicates in Knowledge
Orchestrator: final report.

### Batch files (3+)
Via superpowers:dispatching-parallel-agents.
One agent per file. Orchestrator checks quality.

## Self-Client Mode

When the user consults any financial worker (WRK-005, WRK-006, WRK-009, WRK-018)
or the career specialist about their own situation — this is self-client mode.

Additional rule: after the session, extract personal insights and save:
- Financial decisions / risk profile / goals → `01 Me/Finance.md`
- Career decisions / priorities → `01 Me/Career.md`
- General personal decisions → `01 Me/Profile.md`

Entry format: type decision, date, brief decision or conclusion summary.
This is not a client project report — it is an update to knowledge about the user.

## Key File Paths

- User profile: 01 Me/Profile.md
- Career: 01 Me/Career.md
- Personal finances: 01 Me/Finance.md (create on first access)
- Dashboard: 00 Home/Dashboard.md
- Templates: templates/
- Vault spec: ~/docs/superpowers/specs/2026-06-30-personal-kb-design.md
