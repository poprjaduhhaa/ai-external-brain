# Hub: Ideas

Mode: rapid capture and deep idea analysis.

Subfolders:
- fleeting/ -- quick thoughts without analysis
- analyzed/ -- completed full C-suite review
- creative/ -- creative projects, non-business
- someday/ -- things to do someday

RULES:
- fleeting/ is never analyzed automatically
- Analysis only on explicit user trigger
- Ideas that passed analysis (verdict: viable) move to 02 Projects/

## Workflow: "think through idea: [X]" -- Filter

Use the `council` skill.
Council acts as a philosophical filter before the expensive C-suite analysis.

Three possible outcomes:
1. Green -- proceed to "break down idea: [X]"
2. "What if..." -- Council proposes a specific improvement:
   - Pass to the next Council: what changed + the idea itself
   - Do NOT pass: the previous verdict and its tone (except on the 3rd iteration)
   - Maximum 3 iterations. After the third: pass the full verdict history
   - If the idea still does not pass: either reformulate from scratch or archive
3. Hard no -- archive with a full explanation of why

## Workflow: "break down idea: [X]" -- C-suite Pipeline

Only after a positive Council verdict.

### Phase 1: Analysis (via superpowers:dispatching-parallel-agents)

Six parallel agents. Each invokes the corresponding skill:

**CFO** -- skill: `cfo-review`
- Financial model: revenue, costs, break-even
- ROI: optimistic/realistic/pessimistic
- Runway and capital requirements
- If industry benchmarks needed: sub-agent with `research` + `market-research`

**CMO** -- skill: `cmo-review`
- Market size and ICP
- Competitors: skill `competitive-intel` or `competitive-teardown`
- Acquisition channels realistic for a one-person operation
- CAC estimate

**CTO** -- skill: `cto-review`
- Technically feasible?
- Stack, timeline for a single developer
- Build vs. buy decisions
- If a specific stack assessment is needed: sub-agent with `research`

**COO** -- skill: `coo-advisor`
- Day-to-day operational complexity
- How many people and processes are needed
- What will kill it operationally

**Risk Manager (General Counsel)** -- skill: `gc-review`
- Why this might not work for others who tried
- Legal and regulatory risks (IP, contracts, compliance)
- What will kill it in a year
- For technical risk: additionally `ciso-advisor` if a security angle is needed

**CPO** -- skill: `cpo-review`
- Real problem or infatuation with the solution?
- PMF assessment
- Minimum scope for a first version

After synthesizing the six verdicts -- the orchestrator runs `cross-eval` if the decision is high-stakes (>6 months of time or significant capital).

Director creates a sub-agent if the task requires 3+ sequential searches.
Sub-agent: executes -> self-checks -> reports to Director.
Director: synthesizes -> reports to orchestrator.

### Phase 2: Artifacts (only if verdict is positive)

The orchestrator decides which artifacts are needed based on the type of idea:
- Business: financial model (Sheets) + business plan (Doc) + Drive folder structure
- Tool: tech spec (Doc) + roadmap (Doc)
- Content: content plan (Doc) + monetization calculator (Sheets)

Each artifact begins with:
"What this is, why it was created, how to use it" -- for someone opening it for the first time.

Quality cycle before upload (no iteration limit):
- No broken formulas or empty cells with data
- No TBD, [insert], ???
- Internal logic is consistent
- All cross-references work

After passing: upload to Google Drive, report to user with links.
