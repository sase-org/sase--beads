# Bead: sase-yj.1 — Shared queue grammar and editor contract

[Bead Pages](../README.md) / [sase-yj](README.md) / sase-yj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09b](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09b.md) · **Assignee:** `sase-yj.1` · **Size:** medium
**Created:** 2026-09-08 17:56:09 EDT · **Closed:** 2026-09-08 19:33:29 EDT
**Plan:** [202609/queue\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_directive.md)

## Description

core: implement shared Rust queue validation, formatting, launch parsing, bindings, and completion behind temporary epic scaffolding.

## Notes

[2026-09-08T23:16:42Z · sase-yj.1] PROPOSED FOLLOW-UP: V1 remote dispatch still only rejects %wait/%clan — integration should treat %q/%queue as wait-equivalent so %dispatch %q:5 cannot bypass the restriction once the flag is on.

[2026-09-08T23:33:29Z · sase-yj.1--1] Verified shared Rust %queue/%q contract in sase-core (collect/merge/format, both-states launch parse, admission generation, editor completion/hover/diagnostics, PyO3 bindings, LSP env/initialize pin) behind queue_directive beta flag (default off, bead sase-yl). sase-core ./scripts/check.sh fmt-check, clippy, and test passed with isolated CARGO_TARGET_DIR. just rust-dev-install, just fmt, just lint, targeted pytest (test_queue_directive, test_contract_manifest, test_core_eligibility_facade), and just check (full-suite escalation: core-identity-changed, justfile, src-data-asset) all passed. Thin Python adapter src/sase/xprompt/queue_directive.py added. epic-symbols for this phase: none; leftovers collect_queue_fields, format_queue_directive, queue_directive_flag_key remain keyed to still-open sase-yj.2.

## Dependencies

- **Blocks:** [sase-yj.2](sase-yj.2.md) ◐ · ⧖ 2026-09-08
- **Blocks:** [sase-yj.3](sase-yj.3.md) ◐ · ⧖ 2026-09-08
- **Blocks:** [sase-yj.4](sase-yj.4.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yj.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yj.1.md) | [sase-yj.1](sase-yj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c235300`](https://github.com/sase-org/sase/commit/c235300c6228bdd28f806760bdbd15284aa242c9) | feat(xprompt): add thin Python adapter for shared %queue/%q contract | [sase-yj.1](sase-yj.1.md) | 2026-09-08 19:51:35 EDT |
