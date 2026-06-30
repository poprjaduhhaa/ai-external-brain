# ai-external-brain

> In an era where information moves faster than any individual can process it, the competitive edge belongs to those who connect the right dots at the right time.

![Obsidian](https://img.shields.io/badge/Obsidian-vault-7C3AED?logo=obsidian&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-Code-orange?logo=anthropic&logoColor=white)
![Workers](https://img.shields.io/badge/AI_Workers-19-blue)
![Skills](https://img.shields.io/badge/Skills-242-green)

---

## Why this exists

**Your past self briefs your future self.**
Every session auto-reads your dashboard, inbox, and active projects. Zero re-explaining. Zero lost context.

**A boardroom on demand — in seconds.**
Need a CFO's take on a business model? A lawyer's read on a contract? A CTO's review of your architecture? Deployed in parallel, not days later.

**Expertise that never fabricates.**
Financial rates, library versions, market data — always fetched live via tools. No confident lies dressed as facts.

**Every decision leaves a trace.**
Career moves, financial choices, project pivots — logged, dated, searchable. Your knowledge compounds with every session.

**The system hires its own team.**
New workers are screened by an internal HR agent before entering the library — rejected if methodology is vague, quality gates are missing, or the role is redundant.

---

## System Architecture

Three libraries power everything. The Director orchestrates — workers pull their skills and tools on demand.

```mermaid
graph TB
    Director([Director\nOrchestrator])

    subgraph WLib ["Workers Library — 19 specialists"]
        Core["Core team: QA · PM · Presenter"]
        Domain["Domain: Finance · Research · Career\nEngineering · Strategy · Security · Marketing"]
    end

    subgraph SLib ["Skills Library — 242 skills"]
        SP["Superpowers: systematic-debugging\nwriting-plans · test-driven-development\nverification-before-completion · dispatching-parallel-agents"]
        CS["C-Suite: cfo-review · cmo-review · cto-review\ngc-review · cpo-review · coo-advisor · cross-eval"]
        RS["Research: pulse · dossier · market-research\ncompetitive-intel · litreview · competitive-teardown"]
        CA["Career: tailored-resume-generator\ncold-email · interview-system-designer"]
    end

    subgraph Tools ["MCP Tools — live data, no hallucinations"]
        T1[WebSearch\ncurrent data]
        T2[context7\nlibrary docs]
        T3[markitdown-mcp\nPDF · Word · Excel]
        T4[Gmail · Calendar\nGitHub]
    end

    subgraph Storage ["Persistent Storage"]
        Vault[(Obsidian Vault\nknowledge · decisions · career)]
        GDrive[(Google Drive\norganized folders\nreports · docs · PDFs)]
        Vault -.->|indexed via| DocHub["05 Documents/\nvault index"]
    end

    Director --> WLib
    Director --> SLib
    WLib --> Tools
    WLib --> Storage
```

---

## Request Flow

Every worker carries their own assigned skill set. Skills define HOW they work — tools define WHERE they get data.

```mermaid
flowchart TD
    Input([User Input]) --> Director

    Director[Director\nreads Workers Library\npicks team for this task] --> Router{What kind\nof input?}

    Router -->|idea or\nbig decision| Council

    subgraph IdeaFlow ["Idea Pipeline"]
        Council["council skill\nphilosophical filter"]
        Council -->|iterate max 3x| Council
        Council -->|hard no| Archive[(Archive\n+ reason)]
        Council -->|approved| CSuite

        subgraph CSuite ["C-Suite — 6 parallel agents, each with their own skill"]
            CFO["CFO — cfo-review"]
            CMO["CMO — cmo-review"]
            CTO["CTO — cto-review"]
            COO["COO — coo-advisor"]
            GC["GC — gc-review"]
            CPO["CPO — cpo-review"]
        end

        CSuite --> Stakes{High stakes?\n> 6 months or capital}
        Stakes -->|yes| Cross["cross-eval skill\nmulti-model consensus"]
        Stakes -->|no| QA
        Cross --> QA
    end

    Router -->|research| RA["Research Agent WRK-010\nskills: dispatching-parallel-agents\ntools: WebSearch · context7 · markitdown"]
    Router -->|career / CV / interview| CS["Career Specialist WRK-012\nskills: verification-before-completion\ntools: WebSearch"]
    Router -->|file attached| Doc["markitdown-mcp\nextract → classify → route to hub"]
    Router -->|knowledge /\nlearning| KB["Knowledge Note\n03 Knowledge/"]

    RA --> QA
    CS --> QA
    Doc --> QA
    KB --> QA

    QA["QA Reviewer WRK-001\nskill: verification-before-completion\nchecks every deliverable"]
    QA --> Presenter["Client Presenter WRK-003\nadapts output to audience level"]

    Presenter --> Artifact([Artifact\ndelivered to user])
    Presenter --> GDriveSave[(Google Drive\norganized folders\nPDF · Word · Excel)]
    Presenter --> VaultSave[(Vault Update\nknowledge · decisions\ncareer logs)]
    GDriveSave -.->|indexed in| Index["05 Documents/\nvault index"]
```

---

## Hiring a new worker

```mermaid
flowchart LR
    Gap[Director spots\na skill gap] --> Draft["Drafts spec:\nProcess · Quality Gates\nUncertainty Protocol\ntools + skills assigned"]
    Draft --> HR["HR Agent WRK-004\ninternal screener"]
    HR -->|vague methodology\nmissing QG or protocol| Draft
    HR -->|approved| User[User confirms]
    User --> Library[(Workers Library\nnext ID assigned)]
```

---

## The team

Each worker ships with a defined methodology, quality gates they cannot bypass, and a personal skill + tool set.

| ID | Worker | Skills | Tools |
|----|--------|--------|-------|
| WRK-001 | QA Reviewer | verification-before-completion | markitdown-mcp |
| WRK-002 | Project Manager | verification-before-completion | Gmail · Calendar |
| WRK-003 | Client Presenter | verification-before-completion | Drive · markitdown |
| WRK-004 | HR Agent | verification-before-completion | WebSearch |
| WRK-005 | Financial Modeler | verification-before-completion | markitdown · context7 |
| WRK-006 | Data Analyst | verification-before-completion | WebSearch · context7 · markitdown |
| WRK-007 | Copywriter (Deutsch) | verification-before-completion | context7 |
| WRK-008 | Beverage Expert | verification-before-completion | WebSearch |
| WRK-009 | Broker | verification-before-completion | WebSearch · context7 |
| WRK-010 | Research Agent | dispatching-parallel-agents · verification | WebSearch · context7 · markitdown |
| WRK-011 | Strategy Consultant | brainstorming · verification | WebSearch · context7 |
| WRK-012 | Career Specialist | verification-before-completion | WebSearch |
| WRK-013 | Software Engineer | writing-plans · systematic-debugging · TDD · code-review | context7 · WebSearch |
| WRK-014 | Debugger | systematic-debugging · verification | context7 · WebSearch |
| WRK-015 | Tester | test-driven-development · verification | context7 · WebSearch |
| WRK-016 | Marketer | brainstorming · verification | WebSearch · context7 |
| WRK-017 | Web Developer | writing-plans · TDD · code-review | context7 · WebSearch |
| WRK-018 | Treasury Expert | verification-before-completion | WebSearch · context7 |
| WRK-019 | Cybersecurity Expert | systematic-debugging · verification | WebSearch · context7 |

---

## Stack

| Layer | Tool |
|-------|------|
| Knowledge base | Obsidian |
| AI backbone | Claude Code |
| Document processing | markitdown-mcp |
| Library documentation | context7 MCP |
| Email | Gmail MCP |
| Files | Google Drive MCP |
| Calendar | Google Calendar MCP |
| Version control | GitHub MCP |
| Skills runtime | Superpowers (Anthropic official) + 242 installed skills |

---

## Setup

1. Clone into your Obsidian vault folder
2. Install [Claude Code](https://claude.ai/code)
3. `claude plugin install superpowers@claude-plugins-official`
4. Configure MCP servers per `CLAUDE.md`
5. Open a session from the vault root — Claude reads context automatically

---

*Built with [Claude Code](https://claude.ai/code)*
