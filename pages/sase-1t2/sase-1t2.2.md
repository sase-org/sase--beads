# Bead: sase-1t2.2 — Keep the hijack capability stamp and read the model facts runners actually write

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.2` · **Size:** small
**Created:** 2026-11-15 20:00:08 EST · **Closed:** 2026-11-15 21:12:27 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

meta_facts: fix D3 (runner_capabilities erased by directive extraction) with one shared RUNNER_BOOT_META_KEYS tuple, a runner-side re-stamp, and an invariant test. Fix D4 (wrong model-fact keys, float-only booted_at, monitor/gate classified from live rows or never-written keys) using durable records and a fixture captured from a real runner meta.

## Notes

[2026-11-16T02:12:27Z · sase-1t2.2] D3/D4 meta_facts: shared RUNNER_BOOT_META_KEYS + copy_runner_boot_meta preserve runner_capabilities/code_identity/booted_at/launch_scratch_key/prompt_origin/prompt_source_surface across directive extract; restamp_hijack_capability on same-pid write_agent_meta/bootstrap/followup; stop-target reads llm_provider/exec_llm_provider, model, reasoning_effort, ISO booted_at; monitor/gate from durable records; Python overlay for missing_capability message; captured runner_agent_meta.json fixture; fakey e2e no longer hand-writes capability/legacy keys. Verified: just fix; targeted pytest 28 passed; sase tool run check d2a859ea2686ff3959d7cfc574186b40 succeeded (lint + scoped tests); sase bead epic-symbols sase-1t2.2 had no leftovers. Did not change glossary or sase-core eligibility.rs (core_decision_v2).

## Dependencies

- **Blocks:** [sase-1t2.4](sase-1t2.4.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.2/README.md) | [sase-1t2.2](sase-1t2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bd99aba`](https://github.com/sase-org/sase/commit/bd99aba1c871134b1b7e2c0935d7c0cdf7ce851f) | fix(hijack): preserve runner boot meta and read real model facts | [sase-1t2.2](sase-1t2.2.md) | 2026-11-15 22:35:17 EST |
