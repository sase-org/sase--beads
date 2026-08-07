# Bead: sase-h7.3 — Declarative per-option inputs and per-option submission

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.3` · **Size:** large
**Created:** 2026-08-07 17:07:30 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

inputs-core: add the closed per-option `inputs:` authoring vocabulary built on `InputArg`/`InputType` (plus a new `enum` type), compile it into the option's `input_schema` at creation, and teach the executor to accept and persist one input value per selected option instead of one shared blob.

## Dependencies

- **Blocks:** [sase-h7.10](sase-h7.10.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.5](sase-h7.5.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.6](sase-h7.6.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.8](sase-h7.8.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.9](sase-h7.9.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-h7.3.md) | [sase-h7.3](sase-h7.3.md) | 0 |
