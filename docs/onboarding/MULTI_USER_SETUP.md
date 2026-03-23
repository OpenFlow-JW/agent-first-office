# Multi-user setup (Teams)

AFO is designed to work when different functions run their own agents on their own PCs.

## Default assumption
- Each person runs their local agent (e.g., Claude Code) on their machine.
- Shared state lives in the **SSOT Git repo**.

## API keys: can one person set it up for everyone?
### Option A — BYOK (simple, PoC-friendly)
- Each user supplies their own API key locally.
- Pros: no shared secrets, easy to start.
- Cons: inconsistent configs, harder to manage at scale.

### Option B — Org key via a proxy service (recommended for scale)
- One team operates a small internal service ("AFO Runner") that holds the API key(s).
- Users authenticate to the runner; the runner calls the LLM.
- Pros: centralized key mgmt, governance, audit.
- Cons: requires engineering.

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
