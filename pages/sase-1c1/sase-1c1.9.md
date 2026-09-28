# Bead: sase-1c1.9 — Split the two oversized modules and clear the masked lint tail

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.9` · **Size:** medium
**Created:** 2026-09-28 07:09:35 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

toobig-lint-tail: split src/sase/core/tool_run.py and src/sase/tool/executor.py below 1000 lines along existing seams, then run every CI lint-job step in order and fix what validate, validate-committed-plans, and build-check report now that they finally run.

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1c1.9/README.md) | [sase-1c1.9](sase-1c1.9.md) | 0 |
