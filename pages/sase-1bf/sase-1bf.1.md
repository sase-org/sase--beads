# Bead: sase-1bf.1 — Managed temp root registry the reaper follows

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.1` · **Size:** medium
**Created:** 2026-09-27 14:23:30 EDT · **Closed:** 2026-09-27 17:22:18 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

root-registry: every root `get_sase_managed_tmpdir()` writes into is recorded in a Rust-owned registry under SASE_HOME, and every managed-tmp reaper entry point reaps all registered roots instead of only the root its own environment resolves.

## Notes

[2026-09-27T20:03:33Z · sase-1bf.1--1] PROPOSED FOLLOW-UP: sase-core check clippy fails on clean-tree lints in agent_runtime, agent_scan, finalizer decode, fleet_owner_facts, provider_usage, tool_run receipt/triage (manual_range_contains, nonminimal_bool, collapsible_if); no errors in managed_tmp_roots/managed_tmp touched files; needs clippy baseline update

[2026-09-27T20:13:52Z · sase-1bf.1--2] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on rule closed_survives: closed flag bead sase-1b5 still has surviving ace_final_deck definition in src/sase/feature_flags/registry.py; bead status and registry untouched by phase sase-1bf.1 (diff is managed-tmp/docs only), so failure is pre-existing and independent of root-registry work; needs owner of sase-1b5 to remove the definition or reopen the bead

[2026-09-27T21:22:18Z · sase-1bf.1--a] Closed by explicit `sase stitch create -B close` after create_commit landed 40295eaf54 ("feat(managed-tmp): add Rust-owned root registry the reaper follows (sase-1bf.1)"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1bf.1` if more work remains.

## Dependencies

- **Blocks:** [sase-1bf.3](sase-1bf.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.4](sase-1bf.4.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.6](sase-1bf.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.1.md) | [sase-1bf.1](sase-1bf.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`40295ea`](https://github.com/sase-org/sase/commit/40295eaf543f8e64e1e34c0862bce1411a353a42) | feat(managed-tmp): add Rust-owned root registry the reaper follows (sase-1bf.1) | [sase-1bf.1](sase-1bf.1.md) | 2026-09-27 17:19:10 EDT |
| sase-core | [`sase-core@924884e`](https://github.com/sase-org/sase-core/commit/924884e81b7c69aa2b30714a6cb2a9adac99484f) | feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1) | [sase-1bf.1](sase-1bf.1.md) | 2026-09-27 17:32:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bf.1--a][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.1.md

<!-- sase:referenced-by:end -->
