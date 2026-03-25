# AFO Workflow: Markdown Shared State (Research → Plan → Annotate → Todo → Implement)

This project uses a disciplined pipeline inspired by the “markdown shared state” approach.

## Principle
**Never let the agent implement until a written plan has been reviewed and approved by a human.**

## Files (shared mutable state)
For each work item, create a folder under `docs/work/` (or a PR branch folder) containing:
- `research.md` — deep understanding of existing system/context
- `plan.md` — detailed implementation plan (approach, file paths, snippets, trade-offs)
- `todo.md` — granular task checklist; used as a progress tracker during implementation

## Loop
1) Research: deep read → write `research.md`
2) Planning: write `plan.md`
3) Annotation cycle: human adds inline notes into `plan.md` → agent updates plan (repeat 1–6x)
   - Always include: **“don’t implement yet”**
4) Todo list: generate `todo.md` aligned to the plan
5) Implementation: execute tasks and mark `todo.md` items as completed
6) Feedback: terse corrections; revert + rescope if direction is wrong

## Standard prompts (copy/paste)
### Research
> Read this area in depth, understand how it works and all its specificities. When done, write a detailed report in `research.md`. Do not implement.

### Plan
> Based on `research.md`, write a detailed `plan.md`. Include approach, file paths to change, code snippets, and trade-offs. Do not implement.

### Annotation cycle
> I added notes to `plan.md`. Address every note and update the document accordingly. **Don’t implement yet.**

### Todo list
> Add a detailed `todo.md` aligned to `plan.md`, with phases and individual tasks. Don’t implement yet.

### Implementation
> Implement it all. As you complete tasks/phases, mark them as completed in `todo.md` (and/or plan). Do not stop until all tasks are completed. Continuously run typecheck/tests. Keep changes minimal and clean.

## Cost control rules (practical)
- Trigger-first reviews (don’t auto-run on every change)
- Scope-limited deep reads (specify folders/files)
- Diff-first context (start from PR diff)
- Single-agent default; multi-agent is optional
- Policies sync by release/version

## Why this matters for AFO
- AFO’s core promise is reducing review/approval bottlenecks.
- The plan/todo artifacts become the review surface for both humans and agents.
- The annotation cycle is where domain judgement is injected.
