# Bead: sase-so.1 — Preserve grouped identity through typed launch planning

[Bead Pages](../README.md) / [sase-so](README.md) / sase-so.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c6.md) · **Assignee:** `sase-so.1` · **Size:** medium
**Created:** 2026-08-24 07:02:26 EDT · **Closed:** 2026-08-24 07:49:25 EDT
**Plan:** [202608/toobig\_split\_identity\_tribe.md](https://github.com/sase-org/sase--plans/blob/main/202608/toobig_split_identity_tribe.md)

## Description

typed_identity: extend the Rust/Python typed wire, restore grouped directives, and resolve keyed markers once per batch.

## Notes

[2026-08-24T11:49:25Z · sase-so.1] Verified typed planning keeps %id grouping keywords and %clan (plain, joiner, declarer+tribe/summary, family, named/auto tribe) on AgentUnitWire, reconstructs them via agent_unit_dispatch_prompt matching extract_prompt_directives, deserializes schema-v1 bundles as plain identity, and resolves a shared keyed clan marker once across declarer/joiner/wait/prose while leaving fenced and disabled markers literal. sase-core agent_launch tests plus ./scripts/check.sh fmt+clippy and tests (with PYO3_PYTHON/libpython) passed; sase just install, focused typed-identity tests, and just check passed (scoped lane escalated to the full suite for core-identity-changed).

## Dependencies

- **Blocks:** [sase-so.2](sase-so.2.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-so.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-so.1/README.md) | [sase-so.1](sase-so.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`abefcc4`](https://github.com/sase-org/sase/commit/abefcc4fba5f44198d4375e8ed865b37a81b5c0d) | feat(agent-launch): keep clan and family identity through typed planning | [sase-so.1](sase-so.1.md) | 2026-08-24 07:50:43 EDT |
