# Bead: sase-1ig.6 — sase-core pairing and pre-swap preparation

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.6` · **Size:** medium
**Created:** 2026-10-08 18:23:30 EDT · **Closed:** 2026-10-08 21:04:46 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

dev-core-prep: implement the core pairing rule (resolve, clone, fetch, fast-forward, pin containment), the `--sync` fatal sync gate, the version-window check, the SASE_ALLOW_STALE_CORE escape hatch, and the pre-swap build check, all surfaced as dev plan rows.

## Notes

[2026-10-09T01:04:16Z · sase-1ig.6] Pre-swap build-check timing NOT measured: this workspace has no sase-core checkout in scope (../sase-core absent, SASE_CORE_DIR unset) and no cargo/maturin toolchain (only git+uv present), so cold/warm `maturin build --profile dev-update` timings could not be recorded. engine-dev land agent: from the durable checkout run `time uv run --no-project --with maturin maturin build --profile dev-update --out <tmp> --manifest-path <core>/crates/sase_core_py/Cargo.toml` twice (cold, then warm) with CARGO_TARGET_DIR=<core>/target/uv-tool-py and record both here; warm must reuse artifacts or the cargo-check fallback stays.

[2026-10-09T01:04:30Z · sase-1ig.6] dev-core-prep design deltas: (1) SASE_ALLOW_STALE_CORE=1 also downgrades rule-2 fetch failures to stale warning rows (offline bisect case), not just rule-4/floor. (2) -n --sync with a failing repo exits 1 with the boxed report on stdout; JSON uses outcome=error plus a per-repo sync list. (3) sync report shrinks long paths from the front so the per-repo outcome is never truncated away. (4) pre-swap build check is implemented+tested (maturin-build preferred, cargo-check when uv absent) but NOT wired into any run path yet -- engine-dev calls pre_swap_build_check(core, tool_python) pre-lock. (5) consequential keep rows (dirty/stale core) break plan.noop; proven no-op for all existing plans.

[2026-10-09T01:04:46Z · sase-1ig.6] dev-core-prep done: tools/_sase_install_core.py (pairing rules 1-5, --sync fetch/report/merge gate, version-window check, STALE hatch, maturin/cargo pre-swap build check) wired into build_plan dev core rows + entry (-n --sync report, pairing fatal exit 1). Verified: 107 tests/sase_install pass (3 new files: pairing/sync/build-check with real git repos, containment parity vs core_pin, FF parity vs refresh_clean_linked_checkout), ruff+format clean, extensionless-tools mypy clean, pyscripts valid, epic-symbols empty. Build-check cold/warm timings deferred to engine-dev (no core checkout/toolchain here; noted on bead).

## Dependencies

- **Depends on:** [sase-1ig.2](sase-1ig.2.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.8](sase-1ig.8.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.6/README.md) | [sase-1ig.6](sase-1ig.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62f2560`](https://github.com/sase-org/sase/commit/62f256008be1f469d5315f9b418cd5ab6088a11b) | feat(install): implement dev-core-prep phase (core pairing, sync gate, pre-swap build check) | [sase-1ig.6](sase-1ig.6.md) | 2026-10-08 21:06:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ig.6][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.6/README.md

<!-- sase:referenced-by:end -->
