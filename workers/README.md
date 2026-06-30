---
type: index
hub: workers
date: 2026-06-30
---

# Workers Library

Library of verified workers for client projects.
Each file: role + methodology + quality gates + uncertainty protocol.

Identifier format: WRK-XXX (ID search works in any context)

## Core (always in team)

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-001 | QA Reviewer | qa-reviewer.md | Review all deliverables before delivery |
| WRK-002 | Project Manager | project-manager.md | Scope, timeline, client expectations |
| WRK-003 | Client Presenter | client-presenter.md | Adapt output to client level |

## Meta (internal processes)

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-004 | HR Agent | hr-agent.md | Validate new workers before library entry |

## Domain: Finance & Analytics

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-005 | Excel / Financial Modeler | excel-modeler.md | Financial models, DCF, scenario analysis |
| WRK-006 | Data Analyst | data-analyst.md | Data analysis, insights, visualization |
| WRK-009 | Broker (Securities & Investment) | broker.md | Investment instrument selection, deal structuring |
| WRK-018 | Treasury Expert | treasury-expert.md | Cash management, liquidity, FX, working capital |

## Domain: Research & Strategy

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-010 | Research Agent | research-agent.md | Verified research, due diligence, source synthesis |
| WRK-011 | Strategy Consultant | strategy-consultant.md | Strategic options, OKR, scenario planning, competitive strategy |
| WRK-012 | Career Specialist | career-specialist.md | CV/CL DE+EN, interview prep, ATS, cold outreach, DACH market |

## Domain: Engineering & Development

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-013 | Software Engineer | software-engineer.md | Architecture, backend, API, system design |
| WRK-014 | Debugger | debugger.md | Root cause analysis, error tracing |
| WRK-015 | Tester (QA Engineer) | tester.md | Test strategy, writing tests, edge cases |
| WRK-017 | Web Developer | web-developer.md | Frontend, React/Next.js, responsive, deployment |

## Domain: Marketing & Growth

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-016 | Marketer | marketer.md | Digital marketing, positioning, content, channels |

## Domain: Content & Communication

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-007 | Copywriter (Deutsch) | copywriter-de.md | Professional German text, DACH market |
| WRK-008 | Beverage Expert | beverage-expert.md | Bar menus, beverage concepts, F&B |

## Domain: Security

| ID | Worker | File | Specialization |
|----|--------|------|----------------|
| WRK-019 | Cybersecurity Expert | cybersecurity.md | Pentest, threat modeling, AI security, prompt injection, compliance |

## Role: Director

Director is not a separate file — it is Claude's own role in the context of a client project.
Director reads this README, selects workers from the library, coordinates the team.
Director instructions: ~/projects/personal-kb/07 Clients/CLAUDE.md

## Adding a New Worker

Instructions: workers/CLAUDE.md
Process: Director → HR (WRK-004) → user confirmation → README updated
Next available ID: WRK-020
