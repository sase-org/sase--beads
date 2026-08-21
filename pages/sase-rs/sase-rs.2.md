# Bead: sase-rs.2 — Adopt the released core binding floor

[Bead Pages](../README.md) / [sase-rs](README.md) / sase-rs.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md) · **Assignee:** `sase-rs.2` · **Size:** small
**Created:** 2026-08-21 13:58:40 UTC · **Closed:** 2026-08-21 15:45:11 UTC
**Plan:** [202608/feature\_flag\_control\_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)

## Description

floor: wait for the core release, raise sase's sase-core-rs dependency floor, refresh the lockfile and editable install, and smoke-test the published bindings before Python callers land.

## Notes

[2026-08-21T14:59:56Z · sase-rs.2] Progress: declared feature_flag_state_get/set in check_sase_core_rs_bindings and validate_sase_core_rs, added smoke_sase_core_rs_feature_flag_state, wired CI. Local source-built core (c04a219) exposes the bindings. Floor still >=0.29.5 because PyPI 0.29.5 does not include them. Unblocked sase-core CI with clippy fix e5181a6; waiting for release-plz PR sase-org/sase-core#152 (v0.29.6) to publish.

[2026-08-21T15:01:39Z · sase-rs.2] PROPOSED FOLLOW-UP: just check _lint-flags fails on live flag bead sase-rc (key artifact_links) with no registry definition — unrelated to the core floor; created by sase-r8.3. Do not add artifact_links from this epic.

[2026-08-21T15:44:50Z · sase-rs.2--1] PROPOSED FOLLOW-UP: just check _lint-flags fails on closed flag beads sase-qq (plugin_catalog_scoped_latest) and sase-qf (prettier_enabled) that still have surviving registry definitions — unrelated to the core floor; do not remove those flags from this epic.

[2026-08-21T15:45:11Z · sase-rs.2--1] Verified published sase-core-rs 0.29.6 on PyPI exposes feature_flag_state_get/set. Throwaway venv installed sase-core-rs==0.29.6 and tools/smoke_sase_core_rs_feature_flag_state passed (empty get, two distinct sets survive, same-value set idempotent). Raised inclusive floor to sase-core-rs>=0.29.6,<0.30.0, refreshed uv.lock, just install built linked sase-core v0.29.6. probe_core_floor --advisory, validate_sase_core_rs_version, check_sase_core_rs_bindings, and validate_sase_core_rs all passed; 85 focused floor/binding tests passed. No Python facade imports of the new bindings. sase bead epic-symbols sase-rs.2 had no leftovers. just check still fails only on unrelated pre-existing gates (flag beads sase-qq/sase-qf/sase-rc, symvision private-imports, toobig declaration.py).

[2026-08-21T15:46:40Z · sase-rs.2--1] Verified published sase-core-rs 0.29.6 on PyPI exposes feature_flag_state_get/set. Throwaway venv installed sase-core-rs==0.29.6 and tools/smoke_sase_core_rs_feature_flag_state passed (empty get, two distinct sets survive, same-value set idempotent). Raised inclusive floor to sase-core-rs>=0.29.6,<0.30.0, refreshed uv.lock, just install built linked sase-core v0.29.6. probe_core_floor --advisory, validate_sase_core_rs_version, check_sase_core_rs_bindings, and validate_sase_core_rs all passed; 85 focused floor/binding tests passed. No Python facade imports of the new bindings. sase bead epic-symbols sase-rs.2 had no leftovers. just check still fails only on unrelated pre-existing gates (flag beads sase-qq/sase-qf/sase-rc, symvision private-imports, toobig declaration.py).

## Dependencies

- **Depends on:** [sase-rs.1](sase-rs.1.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-rs.3](sase-rs.3.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rs.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rs.2.md) | [sase-rs.2](sase-rs.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e5181a6`](https://github.com/sase-org/sase-core/commit/e5181a69d20f904f63499387623b6097ad39b80e) | fix(clippy): use Option::unwrap\_or in pull-request URL parser | [sase-rs.2](sase-rs.2.md) | 2026-08-21 14:56:37 UTC |
| sase | [`f355faa`](https://github.com/sase-org/sase/commit/f355faa969513ae0bf09d27423240c3d0f167e03) | build(deps): raise sase-core-rs floor to 0.29.6 | [sase-rs.2](sase-rs.2.md) | 2026-08-21 15:48:29 UTC |
