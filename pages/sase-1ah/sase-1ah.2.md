# Bead: sase-1ah.2 — Add the Rust receipt contract and durable store

[Bead Pages](../README.md) / [sase-1ah](README.md) / sase-1ah.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0st](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0st.md) · **Assignee:** `sase-1ah.2` · **Size:** large
**Created:** 2026-09-26 07:29:31 EDT · **Closed:** 2026-09-26 09:10:11 EDT
**Plan:** [202609/tool\_e4\_verified\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e4_verified_completion.md)

## Description

rust-receipts: add additive schema-1 receipt storage, strict mint and invalidation rules, typed lookup refusals, retention, bindings, and compatibility tests.

## Notes

[2026-09-26T13:10:11Z · sase-1ah.2] rust_receipts: just fmt clean; just test -p sase_core receipt 38 passed; just test -p sase_core_py tool_run_receipt 1 passed; sase tool run check had 1 unrelated sase_gateway flake post_spawn_publish_failure_reaps_barred_worker which passes in isolation

[2026-09-26T13:10:28Z · sase-1ah.2] PROPOSED FOLLOW-UP: investigate sase_gateway post_spawn_publish_failure_reaps_barred_worker flake under full check (passes in isolation)

## Dependencies

- **Depends on:** [sase-1ah.1](sase-1ah.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ah.3](sase-1ah.3.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.2.md) | [sase-1ah.2](sase-1ah.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9f86897`](https://github.com/sase-org/sase-core/commit/9f86897f834e9719c44f5e1669a4bd55d312b99c) | feat(tool-run): add schema-1 receipt contract and durable store | [sase-1ah.2](sase-1ah.2.md) | 2026-09-26 09:12:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ah.3][1] | Need neighboring phase boundaries for core-pin-catalog | 1 |
| read-by | [agent:sase-1ah.4][2] | need phase 2 scope | 1 |
| read-by | [agent:sase-1ah.7][3] | Need sibling phase close evidence for landing-proof | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.7/README.md

<!-- sase:referenced-by:end -->
