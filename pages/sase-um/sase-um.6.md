# Bead: sase-um.6 — Pin the Rust core revision CI builds

[Bead Pages](../README.md) / [sase-um](README.md) / sase-um.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ek](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md) · **Assignee:** `sase-um.6` · **Size:** medium
**Created:** 2026-08-26 19:12:27 EDT · **Closed:** 2026-08-27 09:40:34 EDT
**Plan:** [202608/release\_gate\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)

## Description

corepin: record a sase-core revision in-repo, build CI's core wheel from that revision instead of unpinned HEAD, and add a ratchet path that proposes bumps so a sase-core push can no longer redden sase master on its own.

## Notes

[2026-08-27T13:39:09Z · sase-um.6] PROPOSED FOLLOW-UP: just check fails at lint (feature flags) on a clean master — rule 7: closed flag bead "sase-ul" still has a surviving "link_pager" definition in src/sase/feature_flags/registry.py and src/sase/pager/. Confirmed pre-existing and unrelated to sase-um.6 via git stash on an unmodified tree. Blocks every agents plain `just check` right now; likely a `ci` or `bug` task bead to either retire the link_pager flag or reopen/relink sase-ul.

[2026-08-27T13:39:52Z · sase-um.6] PROPOSED FOLLOW-UP: tests/ace/tui/test_artifacts_relation_collapse.py::test_expanded_link_row_renders_edge_metadata and ::test_dot_collapses_and_expands_on_each_relations_pane fail on a clean, unmodified master (confirmed via git stash) with "ref:plan relation panel stayed hidden". Unrelated to sase-um.6 (ACE artifacts UI, not CI/core-pin). Likely a `bug` task bead.

[2026-08-27T13:40:34Z · sase-um.6] Recorded sase-core-revision.txt as the pinned source-of-truth revision; both master-gate.yml's core-wheel job and ci.yml's build-core job now resolve it from that file (checkout+read, no more git ls-remote HEAD / unpinned checkout) before checking out sase-core, keeping the gate's cache key and wheel deterministic per sase SHA. Added tools/check_sase_core_rs_bindings --remedy and a new 'Check pinned core bindings' step (byte-identical in both lint jobs) so a stale pin fails legibly with the missing binding names and names the bump as the remedy. Added tools/ratchet_core_revision (mirrors tools/ratchet_core_window's --check/--report-only/apply contract) plus .github/workflows/core-pin-ratchet.yml, a schedule+workflow_dispatch-only workflow that proposes a bump PR when sase-core's remote HEAD moves past the pin -- never on push, so it can't itself redden the gate; the opened PR still runs normal per-ref CI. tools/probe_core_floor's advisory role over the published PyPI window is untouched. Verified: just refresh-contract-manifest + just fmt; just check's lint gates all pass except the pre-existing, unrelated 'lint (feature flags)' failure (rule 7 / sase-ul / link_pager), confirmed via git stash on a clean master and noted as a follow-up. just test-scoped: 37812 passed, only the two pre-existing/unrelated ace/tui/test_artifacts_relation_collapse.py failures remain (also confirmed pre-existing via stash, also noted as a follow-up). Bumped the contract-manifest entry budget 58->60 with measured serial cost (31.85s) for the toobig-driven test_github_actions_ci.py split and the new tools/ratchet_core_revision guard. sase bead epic-symbols sase-um.6 reported no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-um.1](sase-um.1.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-um.3](sase-um.3.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-um.8](sase-um.8.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.6/README.md) | [sase-um.6](sase-um.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a8e72ce`](https://github.com/sase-org/sase/commit/a8e72cebeb234ff9a7c69483bc4ee800fd6e5ec8) | feat(ci): pin the sase-core revision CI builds from | [sase-um.6](sase-um.6.md) | 2026-08-27 09:41:48 EDT |
