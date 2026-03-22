# IP / Public vs Private Policy (Draft)

## Goal
We want broad adoption and contributions to the open core, while keeping certain domain skill templates private as potential IP.

## Open core (public)
- Core framework: templates, review lenses framework, reviewer output format, miner format (generic)
- Tooling glue: parsers, validators, CLI/MCP stubs, test harness

## Private (not in this repo)
- Domain-specific `skill.md` templates that encode proprietary decision logic or customer-specific checklists.
- Customer data, internal policies, private prompts.

## How to contribute safely
- If a contribution includes customer specifics or proprietary checklists, it should not be submitted to this repo.
- Prefer contributing generic abstractions and examples with synthetic data.
