# Bead: sase-xq.3 — Settle the shared beads store and require the fixed core

[Bead Pages](../README.md) / [sase-xq](README.md) / sase-xq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0h2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0h2.md) · **Assignee:** `sase-xq.3` · **Size:** small
**Created:** 2026-09-06 17:12:38 EDT · **Closed:** 2026-09-06 20:05:23 EDT
**Plan:** [202609/beads\_projection\_determinism.md](https://github.com/sase-org/sase--plans/blob/main/202609/beads_projection_determinism.md)

## Description

store-reheal-and-pin: raise the sase-core-rs floor to the fixed release, reproject the shared beads store once with doctor --fix-projection, and verify the store stays clean.

## Notes

[2026-09-06T21:38:32Z · sase-xq.3] BLOCKED: fixed core commit 530a1c0 is not available in a published sase-core-rs release; PyPI latest 0.32.28 still contains the link mutation updated_at divergence, so the Python dependency floor cannot be safely raised and the shared store should not be declared settled yet.

[2026-09-06T23:36:49Z · sase-xq.3] PROPOSED FOLLOW-UP: investigate intermittent clan summary SIGTERM timeout test — just check failed once in tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_exits_on_sigterm_without_sigkill, and the exact test passed on immediate rerun.

[2026-09-07T00:05:23Z · sase-xq.3] Raised sase-core-rs floor to >=0.32.30,<0.33.0 and regenerated uv.lock; fixed rust-lsp-install so just install installs sase-xprompt-lsp 0.32.30; verified just install, published-minimum validation, core-floor probe status ok, doctor --fix-projection no drift, sync clean, export_jsonl left beads git clean, targeted LSP parity tests pass, just check passes, and epic-symbols reports no entries.

## Dependencies

- **Depends on:** [sase-xq.1](sase-xq.1.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xq.3/README.md) | [sase-xq.3](sase-xq.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4c3dace`](https://github.com/sase-org/sase/commit/4c3dace967966f1ef544a539f4922fc7236bd6a5) | fix(build): require fixed core and install lsp from isolated target | [sase-xq.3](sase-xq.3.md) | 2026-09-06 20:20:33 EDT |
