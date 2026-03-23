# Multi-user setup (Teams)

AFO is designed to work when different functions run their own agents on their own PCs.

## Default assumption
- Each person runs their local agent (e.g., Claude Code) on their machine.
- Shared state lives in the **SSOT Git repo**.

## API keys: can one person set it up for everyone?
### Option A — BYOK (simple, PoC-friendly) ✅ Start here
- Each user supplies their own API key locally.
- Pros: no shared secrets, easy to start.
- Cons: inconsistent configs, harder to manage at scale.

### Option B — Org key via a proxy service (recommended for scale) 🔜 Roadmap
- One team operates a small internal service ("AFO Runner") that holds the API key(s).
- Users authenticate to the runner; the runner calls the LLM.
- Pros: centralized key mgmt, governance, audit.
- Cons: requires engineering.

## PoC recommended flow (BYOK, 10 minutes)
1) Clone the repo (or download as zip)
2) Create your personal soul file:
   - Copy `souls/SOUL.template.md` → `souls/<YourName>.<Role>.SOUL.md`
   - Answer the questions in `docs/onboarding/SETUP_QUESTIONS.md`
3) Prepare a PRD:
   - Copy `docs/PRD.template.md` into `PRD/<feature>.md`
4) Run the workflow with your local agent (Claude Code):
   - Generate `research.md` → `plan.md` → annotate → `todo.md`
   - Ensure “don’t implement yet” until plan is approved
5) Open a PR to the SSOT repo
6) Trigger a review lens (UX) and paste the report as a PR comment
7) Signoff via PR Approve (PM/Dev as minimum)

Tip: keep the first PRD tiny. The goal is to prove the loop, not perfection.

### Option C — GitHub Actions key (CI-style)
- Store keys in GitHub Actions secrets.
- Use Actions to run review jobs.
- Pros: centralized secrets.
- Cons: slower feedback loop than local.

**Never commit API keys into the repo.**

## Minimal team to start
You do NOT need every function present.
- Smallest viable team: **PM + Dev**
- Next: PM + UX (better PRD quality)
- Add QA later for robustness

## Collaboration loop
- Agents can work asynchronously; signoff happens via PR approvals.
