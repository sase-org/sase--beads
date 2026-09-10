# Bead: sase-xe.16.11.7.14.2 — Close the dismissal identity leak and reconcile history

[Bead Pages](../README.md) / [sase-xe.16.11.7.14](sase-xe.16.11.7.14.md) / sase-xe.16.11.7.14.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0it](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0it.md) · **Assignee:** `sase-xe.16.11.7.14.2` · **Size:** medium
**Created:** 2026-09-10 13:39:04 EDT · **Closed:** 2026-09-10 15:38:35 EDT
**Plan:** [202609/fleet\_stale\_remote\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md)

## Description

dismissal-reconcile: extend the cleanup cascade to cover member records discovered from the index, add gc back-fill of dismissal identities for dead members of dismissed families, and surface silent index-sync failures.

## Notes

[2026-09-10T19:14:25Z · sase-xe.16.11.7.14.2] PROPOSED FOLLOW-UP: feature flag registry/call-site audit blocks full just check - tools/check_feature_flags reports live flag bead sase-z0/link_events has no registry definition, and this checkout has no FeatureFlag.link_events non-test call site.

[2026-09-10T19:38:35Z · sase-xe.16.11.7.14.2] Verified cargo test -p sase_core dismissal_reconcile_backfills_dead_family_members_only, cargo check -p sase_core_py, local rust-install from edited core plus tools/check_sase_core_rs_bindings, ruff/compileall, and focused pytest 10 passed. just check rerun passes fmt/ruff/mypy and stops at unrelated rule 8 live flag bead sase-z0/link_events missing registry definition; PROPOSED FOLLOW-UP noted.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.14.3](sase-xe.16.11.7.14.3.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.2/README.md) | [sase-xe.16.11.7.14.2](sase-xe.16.11.7.14.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f22339c`](https://github.com/sase-org/sase/commit/f22339c182702051cd2d8dd104414912721e8172) | fix(agent-index): reconcile dismissed family identities | [sase-xe.16.11.7.14.2](sase-xe.16.11.7.14.2.md) | 2026-09-10 15:40:21 EDT |
