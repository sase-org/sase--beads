# Bead: sase-jx.5.3 — Ratchet the published core dependency contract

[Bead Pages](../README.md) / [sase-jx.5](sase-jx.5.md) / sase-jx.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-jx.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.land/README.md) · **Assignee:** `sase-jx.5.3` · **Size:** small
**Created:** 2026-08-12 12:14:59 EDT · **Closed:** 2026-08-12 13:28:13 EDT
**Plan:** [202608/land\_axe\_chop\_overrun.md](https://github.com/sase-org/sase--plans/blob/main/202608/land_axe_chop_overrun.md)

## Description

publish_core_floor: after the corrected sase-core release is fully available, use the repository's release-owned ratchet workflow to move pyproject.toml and uv.lock to the first published sase-core-rs version containing the complete corrected chop-overrun schema contract, and verify the floor-pinned binding inventory and schema probe.

## Notes

[2026-08-12T17:28:13Z · sase-jx.5.3] Ratcheted the published core dependency contract with the repository-owned workflow: waited for sase-core-rs 0.26.4 to publish, confirmed PyPI has the complete release set (sdist plus macOS universal2, manylinux x86_64, manylinux aarch64, and Windows x86_64 wheels), then ran UV_NO_CACHE=1 just ratchet-core-window to update pyproject.toml and uv.lock from >=0.24.0,<0.25.0 to >=0.26.4,<0.27.0. Verified git diff contains only the expected pyproject.toml dependency line and uv.lock sase-core-rs stanza/metadata changes; UV_NO_CACHE=1 just ratchet-core-window --report-only now reports the floor already matches newest complete published release 0.26.4. Ran just install and rebuilt linked sase_core/sase_core_py as 0.26.4. Verified published-floor gates: .venv/bin/python tools/validate_sase_core_rs_version --pyproject pyproject.toml --published-minimum; .venv/bin/python tools/probe_core_floor --sase-core-dir <linked sase-core>; scratch Python 3.12 env installed exact sase-core-rs==0.26.4 with editable sase, asserted installed distribution version 0.26.4, chop_overrun_wire_schema_version()==2, and classify_chop_overrun returns schema-v2 aligned run_ratios; scratch env also passed tools/check_sase_core_rs_bindings (293 bindings), tools/validate_sase_core_rs, and the telemetry/at-reference-file/bead-resolution/plan-header/glossary-line-break core smoke scripts. Focused AXE verification passed: pytest tests/test_axe_chop_overrun.py and collector/force-refresh/dashboard overrun/chop tests (37 selected). just check passed all lint/validation gates and scoped pytest, with test-scoped escalating to the full suite due contract-set-only/core-identity-changed/packaging-config.

[2026-08-12T17:29:45Z · sase-jx.5.3] Verified PyPI complete release for sase-core-rs 0.26.4, ratcheted pyproject/uv lock floor, exact-floor smoke passed, focused chop-overrun tests passed, and just check passed.

## Dependencies

- **Depends on:** [sase-jx.5.1](sase-jx.5.1.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-jx.5.2](sase-jx.5.2.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-jx.5.4](sase-jx.5.4.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jx.5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.5.3/README.md) | [sase-jx.5.3](sase-jx.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`688eec2`](https://github.com/sase-org/sase/commit/688eec2bda77374340aef20e0fe948a128401102) | build(deps): ratchet core binding floor | [sase-jx.5.3](sase-jx.5.3.md) | 2026-08-12 13:31:13 EDT |
