# AI Contributing Guide

This project welcomes AI-assisted contributions.

## TL;DR
- Use your own agent (Claude Code / Codex / OpenClaw / Copilot) locally.
- Submit changes via **Fork → Branch → PR**.
- Keep contributions **generic** (no customer/proprietary data).
- Include **DCO sign-off** in commits.

---

## What to contribute (best first)
### 1) Docs & templates (fastest)
- Improve `docs/PRD.template.md`
- Add an example PRD (synthetic)
- Improve onboarding docs

### 2) Review lenses
- Add / improve a lens checklist (e.g., `lens: ux`)
- Add a reviewer report format example

### 3) Tooling (later)
- Validators (frontmatter required fields)
- Report format checks

---

## Recommended workflow
### Step 0 — Pick a task
- Start from `docs/GOOD_FIRST_ISSUES.md` or open a small Issue.

### Step 1 — Fork & clone
```bash
git clone <your-fork-url>
cd agent-first-office
```

### Step 2 — Create a branch
```bash
git checkout -b docs/improve-prd-template
```

### Step 3 — Use an AI agent to draft changes
Your agent should:
- read the relevant file(s)
- propose a small patch
- avoid adding private/proprietary content

#### Example prompt (generic)
> Read `docs/PRD.template.md`. Improve clarity and add one short synthetic example under each section. Keep it concise. Do not add customer-specific content.

### Step 4 — Human review
Before committing:
- skim for correctness and tone
- remove any sensitive content
- ensure it matches the repo style

### Step 5 — Commit with DCO sign-off
```bash
git add -A
git commit -s -m "docs: improve PRD template"
```

### Step 6 — Push and open a PR
```bash
git push -u origin docs/improve-prd-template
```
Open a PR using GitHub UI.

---

## Safety rules (important)
Do NOT contribute:
- customer-specific checklists / decision logic
- internal policies, secrets, tokens
- real datasets, real emails, private conversations

If you want to share a domain-specific checklist, open an Issue and describe it at a high level.

---

## Review expectations
PRs are easiest to merge when they:
- are small and focused
- include acceptance criteria where relevant
- follow the PR template

Thanks for helping build agent-first knowledge work.
