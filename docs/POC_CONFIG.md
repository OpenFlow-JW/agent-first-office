# AFO PoC Config (Claude Code, Git SSOT, Slack)

This document describes the minimum configuration to run an AFO PoC.

## PoC assumptions
- Local agent: **Claude Code** (primary)
- SSOT: **GitHub repo** (PRD repo)
- Collaboration interface: **Git PR + Slack notifications/triggers**
- LLM: external OK, **BYOK** (bring your own key)
- Participants: dev-heavy, with motivated PM/Design joining

---

## Minimal configuration checklist
### 1) Repository
- Create/use a GitHub repo as SSOT for PRDs
- Structure (minimal):
  - `PRD/` (Markdown PRDs)
  - `reviews/` (optional)

### 2) Document type
- Wedge doc: **PRD** (Markdown + frontmatter)

### 3) Review lens
- Start with **UX lens** only
- Output: PR comment report

### 4) Output mode
- `output = pr_comment`
- (optional) also commit report file into the PR branch

### 5) Slack integration (PoC)
Keep it minimal:
- `/afo review <PR_URL>` → generates PR comment report + posts 3-line summary to Slack
- `/afo status <PR_URL>` → posts blockers/signoff status

### 6) BYOK (LLM keys)
- Each runner/operator provides their own API key (Claude/OpenAI/etc)
- Keys must never be committed to the repo

---

## Optional: Multi-agent orchestration (DeepAgent-style)
Multi-agent orchestration can be included as a *framework-level pattern* without forcing heavy setup.

### Why it helps
- Helps scale review and specialization by role:
  - CEO/PM (scope, priorities)
  - UX reviewer (flows, edge cases)
  - QA reviewer (test cases, observability)
  - Dev reviewer (interfaces, feasibility)

### Minimal approach (no new platform required)
Use Claude Code (or your agent runtime) with explicit role prompts and shared markdown state:
- One work folder per PRD:
  - `research.md`, `plan.md`, `todo.md`
- Run subagents sequentially or in parallel, each writing a section into the same artifacts.

### Guardrails
- Planning/execution separation
- One artifact is the source of truth (SSOT)
- Human signoff remains the final gate

---

## Next step
- Add a sample PRD + run UX lens review end-to-end on a real PR.
