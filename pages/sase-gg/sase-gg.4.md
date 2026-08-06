# Bead: sase-gg.4 — Harden the generated sase\_core\_rs package init upstream

[Bead Pages](../README.md) / [sase-gg](README.md) / sase-gg.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.u6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.u6/README.md) · **Assignee:** `sase-gg.4` · **Size:** small
**Created:** 2026-08-06 12:26:41 EDT · **Closed:** 2026-08-06 12:37:28 EDT
**Plan:** [202608/ci\_green\_restore.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restore.md)

## Description

coreinit: fix the maturin star-import template in the sase-core repo so the package init binds the extension module explicitly instead of relying on an importlib side effect.

## Notes

[2026-08-06T16:37:09Z · sase-gg.4] PROPOSED FOLLOW-UP: sase-core wheel-smoke CI job (crates/sase_core_py, .github/workflows/ci.yml) only checks a plain `import sase_core_rs`; it never exercises the del-sys.modules re-import path that caused this defect. Add a re-import smoke check (del sys.modules["sase_core_rs"]; importlib.import_module) to the wheel-smoke and release-plz smoke steps so a regression is caught before publish.

[2026-08-06T16:37:28Z · sase-gg.4] Fixed the root cause in sase-core: crates/sase_core_py now ships an explicit python/sase_core_rs/__init__.py (via python-source = "python" in pyproject.toml) that binds the compiled submodule by name instead of relying on importlib's post-import setattr side effect. Verified by building the wheel with maturin (release build, tag v0.18.4 source), installing into a fresh Python 3.12 venv, and reproducing the exact plan repro: del sys.modules['sase_core_rs'] then re-import now succeeds (previously NameError). Cross-checked that the currently-published wheel (installed in this sase workspace's .venv) still reproduces the original NameError under the same steps, confirming this is a real, fixed defect. __doc__/__all__ re-exports kept byte-compatible; cargo fmt --check passes (no Rust source touched). Opened https://github.com/sase-org/sase-core/pull/89 for review/merge to follow the repo's normal release-plz path; did not merge or publish myself since that triggers automated PyPI publish. Filed a PROPOSED FOLLOW-UP note on this bead for adding a re-import regression check to sase-core's wheel-smoke CI.

## Dependencies

- **Blocks:** [sase-gg.5](sase-gg.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gg.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gg.4/README.md) | [sase-gg.4](sase-gg.4.md) | 0 |
