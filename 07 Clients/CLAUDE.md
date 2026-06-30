# Hub: Clients

Mode: delivery excellence for client projects.

Ideas are not validated here — the client has already hired. Here the goal is to fully meet client needs at the highest level, communicated in a way that is clear to them.

## Structure of Each Client Project

```
07 Clients/[client-name]/
├── CLAUDE.md          — who the client is, their level, communication style
├── brief.md           — finalized brief
├── deliverables/      — what was created and delivered
└── feedback/          — client responses and revisions
```

## Workflow: Client Director

### Step 1: Drafting the Brief (max 3 iterations)

1. User describes the task ("the client needs a bar menu...")
2. Director asks clarifying questions one at a time
3. Collects answers + accepts references from the user
4. Drafts the brief
5. Reads the brief, identifies gaps
6. If gap: asks the user — does NOT hallucinate
7. Max 3 iterations → finalizes brief.md

### Step 2: Team Assembly

Director reads ~/projects/personal-kb/workers/README.md
Selects the needed workers from the library for this specific task.
Constants (always in team): project-manager, qa-reviewer, client-presenter.
Variables (task-dependent): Director decides based on the brief.

If a needed worker is not in the library:
→ Notify the user which worker is needed
→ Start the new worker creation process (see workers/CLAUDE.md)
→ Do not start work without the required worker

### Step 3: Execution

Parallel agents via superpowers:dispatching-parallel-agents.
Each worker: executes → self-review against their quality gates → reports to Director.
QA: reviews all deliverables → reports to Director.
Presenter: adapts to client level → reports to Director.
Director: final approval → report to user.

### Step 4: Sources

Each deliverable contains a reference to data sources and references.
Format in frontmatter: source: [path or original URL]

## Rule: The Client Does Not Read Technical Details

Presenter adapts any output to the client's level.
If the client is non-technical — no formulas without explanation, no jargon.

## Sensitive Data Policy

Client personal data (name, email, financial data, contacts) is stored only in the client folder `07 Clients/[client-name]/`.
Never copy to other vault hubs.
Real tokens, passwords, keys — immediately notify the user, do not log in notes.
If a client file contains confidential data — add `sensitive: true` to frontmatter.
