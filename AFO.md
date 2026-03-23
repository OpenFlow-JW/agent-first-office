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

## Safety
- Never include secrets or customer proprietary content in public artifacts.
