# Bead: sase-i9.5 — End-to-end verification and documentation

[Bead Pages](../README.md) / [sase-i9](README.md) / sase-i9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wj](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wj/README.md) · **Assignee:** `sase-i9.5` · **Size:** small
**Created:** 2026-08-09 10:11:28 EDT · **Closed:** 2026-08-09 17:04:17 EDT
**Plan:** [202608/fast\_dev\_update.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_dev_update.md)

## Description

verify: measure the real `,U` flow against the phase-one baseline, re-exercise every preserved blocker/fallback/restart path on the live dev install, confirm `just install` and CI are unaffected, and refresh the Rust backend docs.

## Notes

[2026-08-09T21:01:36Z · sase-i9.5] PROPOSED FOLLOW-UP: just test / CI test(3.14) hangs near suite completion on Python 3.14 -- pre-existing, not caused by this epic. Evidence: 3/3 independent local `just test` runs on this Python 3.14.3 host stalled at ~99% (406/406 output lines, output frozen) with multiple pytest-xdist workers parked in asyncio base_events select() inside pytest_asyncio inner()/run_until_complete() (py-spy dump, 2026-08-09). GitHub Actions confirms it independently: run 31330235843 (commit "refactor(dev-update): split execution responsibilities", unrelated to sase-i9) shows job test(3.14) running 19:22:19->20:52:34 (~1h30m) before cancellation, while test(3.12) completed cleanly in the same run at 1658s with 28087 passed / 21 failed (unrelated pre-existing ACE footer-visibility flakes) / 49 skipped, and test(3.13) failed (not hung) in ~17min. Needs bisection to find which async test(s) hang under 3.14 specifically; likely a pytest-asyncio/CPython-3.14 event-loop interaction, not app code. Size: medium.

[2026-08-09T21:02:58Z · sase-i9.5] PROPOSED FOLLOW-UP: the Justfile sase_core_dir variable (Justfile:24) falls back through SASE_LINKED_REPO_SASE_CORE_DIR / SASE_SIBLING_REPO_SASE_CORE_DIR before its relative-path default, and every SASE agent process has those env vars exported pointing at its own ephemeral workspace linked-repo clone (confirmed via `env` dump in this session). So any `just rust-install`/`rust-dev-install` invocation run from inside an agent shell -- even with cwd correctly set to the real host checkout -- silently builds sase_core_rs from that agent workspace clone instead of the host sibling repo. This is the same failure class already logged as a DISCOVERED ISSUE note on parent epic sase-i9 (host uv-tool venv broken 2026-08-09 ~11:22 EDT); this note adds the concrete mechanism. A later real `,U` run in the dev_update journal (timestamp 2026-08-09T12:48:31-04:00) shows the "sase-core-rs" package plan entry git_root pointing at this very ephemeral workspace path even though the reconcile command cwd was the host root, reproducing the same class of bug after the incident was first reported. Host is currently healthy (sase_core_rs imports fine and its .pth now points at the host sibling repo), but the underlying gap -- Justfile sase_core_dir resolution trusting workspace-scoped env vars regardless of invocation context -- is still open. Suggested guard (from the epic note): refuse to install an editable extension into a venv from a source root that does not match the host checkout, or scrub SASE_*_SASE_CORE_DIR when just is invoked with cwd outside the current workspace. Size: medium.

[2026-08-09T21:04:17Z · sase-i9.5] Verified: (1) tools/dev_update_timings shows only 1 real timed reconcile-step run exists post-instrumentation (schema-2), from a live host ,U at 2026-08-09T12:48:31-04:00: uv_tool_install 1.0s, rust_dev_install 399.4s (two full cargo compiles -- Plan B separate-CARGO_TARGET_DIR path, per fast_dev_update.md's documented fallback, since the core checkout was dirty so caching couldn't apply), rust_health_check 0.1s; sample size is too small for a pre/post median comparison. (2) Preserved blocker/fallback/restart paths re-exercised via tests/dev_update/ (93 tests incl. new test_produce_refuses_while_update_writer_lock_held) -- all pass; did NOT re-run these against the live host install because this session's SASE_LINKED_REPO_SASE_CORE_DIR/SASE_SIBLING_REPO_SASE_CORE_DIR env vars make any just rust-*-install invoked from this shell silently target this ephemeral workspace's linked sase-core clone instead of the host's sibling repo (see follow-up note), so doing so here risks repeating the exact host-venv corruption already logged on the epic bead; confirmed the host uv-tool venv's sase_core_rs is currently healthy and points at the real host sibling checkout. (3) just install (managed/non-editable-adjacent path) succeeds cleanly and fast (fully cached, <1s cargo). (4) All just check lint gates pass individually (fmt-py, keep-sorted, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig, validate, validate-committed-plans) except fmt-md, which fails only on sase/memory/build_and_run.md -- confirmed pre-existing on master (unrelated to this diff) and already being fixed by a concurrent commit. (5) just test / full suite could not be run to completion locally or via just check's composite recipe: 3 independent attempts hung at ~99% on this Python 3.14.3 host with workers parked in asyncio select() inside pytest_asyncio; confirmed via GitHub Actions history that CI's test(3.14) job independently hangs the same way (~1h30m before cancellation) while test(3.12)/test(3.13) complete, so this is a pre-existing Python-3.14-specific issue unrelated to this diff (recorded as PROPOSED FOLLOW-UP). (6) docs/rust_backend.md refreshed with prebuild default/disable instructions; existing recipe table, dev-update profile, and prebuild cache docs from prior phases already cover the rest of item 4's ask; docs/development.md needs no change (points at rust_backend.md for detail). Recorded 2 PROPOSED FOLLOW-UP notes on this bead: the Python 3.14 test hang, and a concrete mechanism (Justfile:24 env var precedence) explaining the previously-logged host-venv-corruption DISCOVERED ISSUE on the epic.

## Dependencies

- **Depends on:** [sase-i9.1](sase-i9.1.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-i9.2](sase-i9.2.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-i9.3](sase-i9.3.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-i9.4](sase-i9.4.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i9.5/README.md) | [sase-i9.5](sase-i9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4f54489`](https://github.com/sase-org/sase/commit/4f54489af3bd33d069d2ce1a7cd22039844b2822) | test(dev-update): cover prebuild refusal while update writer lock is held | [sase-i9.5](sase-i9.5.md) | 2026-08-09 17:05:17 EDT |
