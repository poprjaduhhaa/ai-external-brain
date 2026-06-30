# Workers Library

Worker library for client projects.
Each worker: a markdown file with verified methodology.

Vault spec: `~/docs/superpowers/specs/2026-06-30-personal-kb-design.md`

## Worker File Format

```markdown
---
id: WRK-XXX
role: [role name]
goal: [what they optimize for in one sentence]
expertise: [domain and expertise level]
always_in_team: true | false
tools: [list of MCP tools]
skills: [list of superpowers skills]
tags: [domain, type]
---

# Worker: [Name]

## Backstory
[Who they are, what experience they have, how they think — 3-5 sentences]

## Process
[Step-by-step process. HOW to think, not WHAT to do.
Concrete domain methodology.]

## Quality Gates
Cannot submit work until each item passes:
- [ ] [specific criterion]

## Uncertainty Protocol
- [situation] → [action: ask / flag / stop]
- Never guess [specifically what]

## Report Format
- What was done
- Assumptions made
- Quality gates passed
- What requires user decision
```

## Creating a New Worker

1. Director drafts worker using the format above
2. Director uses WebSearch/context7 to research real domain methodology
3. Director assigns tools and skills from tables below (Master Mapping)
4. HR Agent (WRK-004) reviews the draft
5. User confirms
6. File added to library and to README.md

## HR Agent Review Criteria

HR rejects if:
- No Process section (only role description)
- Quality Gates are vague ("check quality")
- No Uncertainty Protocol
- No `tools` and `skills` in frontmatter
- No `id` or ID already taken

HR approves if:
- Process describes HOW to think, not WHAT to do
- Quality Gates are specific and self-enforcing
- Clear guidance on when to ask vs. when to act
- Tools and skills match the Master Mapping below

---

## Master: Tools Mapping

Available MCP tools and when to use them:

| Tool | Real system name | When required |
|------|-----------------|--------------|
| `WebSearch` | WebSearch | any current data (prices, rates, competitors, market size, versions) |
| `context7` | mcp__context7__* | library documentation, frameworks, APIs — always current version |
| `markitdown-mcp` | mcp__markitdown__* | processing PDF, Word, any client documents |
| `gmail-mcp` | mcp__claude_ai_Gmail__* | email work (PM, Career Specialist) |
| `google-drive` | mcp__claude_ai_Google_Drive__* | upload / read files from Drive |
| `google-calendar` | mcp__claude_ai_Google_Calendar__* | scheduling, deadlines (Project Manager) |

### Tools by Worker

| ID | Worker | Tools |
|----|--------|-------|
| WRK-001 | QA Reviewer | markitdown-mcp |
| WRK-002 | Project Manager | gmail-mcp, google-calendar |
| WRK-003 | Client Presenter | google-drive, markitdown-mcp |
| WRK-004 | HR Agent | WebSearch |
| WRK-005 | Excel Modeler | markitdown-mcp, context7 |
| WRK-006 | Data Analyst | WebSearch, context7, markitdown-mcp |
| WRK-007 | Copywriter-DE | context7 |
| WRK-008 | Beverage Expert | WebSearch |
| WRK-009 | Broker | WebSearch, context7 |
| WRK-010 | Research Agent | WebSearch, context7, markitdown-mcp |
| WRK-011 | Strategy Consultant | WebSearch, context7 |
| WRK-012 | Career Specialist | WebSearch |
| WRK-013 | Software Engineer | context7, WebSearch |
| WRK-014 | Debugger | context7, WebSearch |
| WRK-015 | Tester | context7, WebSearch |
| WRK-016 | Marketer | WebSearch, context7 |
| WRK-017 | Web Developer | context7, WebSearch |
| WRK-018 | Treasury Expert | WebSearch, context7 |
| WRK-019 | Cybersecurity Expert | WebSearch, context7 |

---

## Skill Discovery

If unclear which skill to use or you need to find a new one:
```bash
ls ~/.claude/skills/
```
All installed skills are in `~/.claude/skills/`. Invoke via Skill tool or `/skill-name`.
Catalog with descriptions: `~/projects/personal-kb/skills/README.md`

## Master: Skills Mapping

Available superpowers skills and when to use them:

| Skill | Purpose |
|-------|---------|
| `superpowers:brainstorming` | designing a solution before coding |
| `superpowers:writing-plans` | creating an implementation plan |
| `superpowers:executing-plans` | executing a plan step by step |
| `superpowers:systematic-debugging` | structured bug investigation |
| `superpowers:test-driven-development` | writing tests before implementation |
| `superpowers:finishing-a-development-branch` | final checks before code delivery |
| `superpowers:requesting-code-review` | requesting review of finished code |
| `superpowers:receiving-code-review` | processing review feedback |
| `superpowers:verification-before-completion` | final verification of any deliverable |
| `superpowers:subagent-driven-development` | complex tasks with subtasks |
| `superpowers:dispatching-parallel-agents` | parallel execution of independent tasks |

### Skills by Worker

| ID | Worker | Skills |
|----|--------|--------|
| WRK-001 | QA Reviewer | verification-before-completion |
| WRK-002 | Project Manager | verification-before-completion |
| WRK-003 | Client Presenter | verification-before-completion |
| WRK-004 | HR Agent | verification-before-completion |
| WRK-005 | Excel Modeler | verification-before-completion |
| WRK-006 | Data Analyst | verification-before-completion |
| WRK-007 | Copywriter-DE | verification-before-completion |
| WRK-008 | Beverage Expert | verification-before-completion |
| WRK-009 | Broker | verification-before-completion |
| WRK-010 | Research Agent | dispatching-parallel-agents, verification-before-completion |
| WRK-011 | Strategy Consultant | brainstorming, verification-before-completion |
| WRK-012 | Career Specialist | verification-before-completion |
| WRK-013 | Software Engineer | writing-plans, systematic-debugging, test-driven-development, requesting-code-review, finishing-a-development-branch |
| WRK-014 | Debugger | systematic-debugging, verification-before-completion |
| WRK-015 | Tester | test-driven-development, verification-before-completion |
| WRK-016 | Marketer | brainstorming, verification-before-completion |
| WRK-017 | Web Developer | writing-plans, test-driven-development, finishing-a-development-branch, requesting-code-review |
| WRK-018 | Treasury Expert | verification-before-completion |
| WRK-019 | Cybersecurity Expert | systematic-debugging, verification-before-completion |

---

## Anti-Hallucination Protocol (required for all workers)

This rule overrides any other worker instruction.

### What is forbidden from internal knowledge

| Category | Forbidden | Required |
|----------|-----------|----------|
| Financial data | exchange rates, interest rates, quotes, yields | WebSearch with date |
| Technical versions | library versions, API syntax, breaking changes | context7 or WebSearch |
| Market data | market size, competitor prices, market share | WebSearch with source |
| Regulatory | tax rates, legal norms, compliance requirements | WebSearch + [VERIFY WITH SPECIALIST] |
| Availability | ingredient/product availability in specific region | WebSearch |

### Marking Rule

If a tool was not used, data must be tagged:
- `[ASSUMPTION: verify currency]` — for data that may have changed
- `[FROM MEMORY — unverified]` — for technical details without context7
- `[VERIFY WITH SPECIALIST]` — for legal and tax statements

### "Stop Before Recommendation" Rule

Before any specific recommendation with numbers: the worker must verify data via tool.
If the tool is unavailable or data not found: provide the recommendation as a framework (how to think about the task), not as specific numbers.
