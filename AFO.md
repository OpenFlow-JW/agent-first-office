# AFO Skill Pack (Draft)

This file defines the default workflow and rules for using coding agents (Claude Code / Codex CLI) within Agent First Office.

## Core principle
- **Do not implement until a written plan has been reviewed and approved by a human.**

## Workflow (repeat 1–6x)
1) Research → write `research.md`
2) Plan → write `plan.md` (**don’t implement yet**)
3) Annotate → human adds inline notes into `plan.md`
4) Update plan → agent updates `plan.md` (don’t implement yet)
5) Todo → write `todo.md` (don’t implement yet)
6) Implement → execute tasks and mark `todo.md` as complete

## Artifacts (shared state)
- `research.md`
- `plan.md`
- `todo.md`

## Lens & reports
- Lenses live under `docs/lenses/`
- Review report templates live under `docs/reports/`

## Cost control rules (PoC-friendly)
- **Trigger-first**: do not run reviews on every change by default; run when requested (Slack command / PR label).
- **Scope-limited reading**: always specify the folder/files to read; avoid “read the whole repo”.
- **Artifacts over chat**: store results in `research.md/plan.md/todo.md` and reference them; don’t re-paste long text.
- **Diff-first**: reviewers should start from PR diff; only pull extra context when needed.
- **Single-agent by default**: multi-agent orchestration is optional; use it only when the task warrants it.
- **Release-based policy sync**: sync policies by version/release, not continuously.

## Safety
- Never include secrets or customer proprietary content in public artifacts.
