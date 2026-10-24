# Bead: sase-1nf.10.1.9.1.6.2 — Make stale-replay recovery binary-safe and merge-base aware

[Bead Pages](../README.md) / [sase-1nf.10.1.9.1.6](sase-1nf.10.1.9.1.6.md) / sase-1nf.10.1.9.1.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10.1.9.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.1.land.md) · **Assignee:** `sase-1nf.10.1.9.1.6.2` · **Size:** medium
**Created:** 2026-10-21 10:45:30 EDT · **Closed:** 2026-10-21 12:07:57 EDT
**Plan:** [202610/publication\_blockers\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_blockers_acceptance.md)

## Description

replay-policy: read upstream blobs as bytes in the stale-replay helper, add an optional merge-base keep-one-side rule to the sase-core replay byte policy, wire it through report and apply, add fixtures, and bump the core pin.

## Notes

[2026-10-21T15:58:18Z · sase-1nf.10.1.9.1.6.2] PROPOSED FOLLOW-UP: Existing TUI startup import-closure overage remains tracked by sase-1ic: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget failed on both the changed tree and detached clean base HEAD 50ef6ba498 at 3529 modules vs the 3527 cap; this phase did not cause it.

[2026-10-21T16:07:57Z · sase-1nf.10.1.9.1.6.2] Implemented merge-base-aware, byte-preserving stale replay across payloads and run state/metadata; added Rust wire/binding logic, integration and unit coverage, and updated docs. Verified focused replay tests, sase-core check (pass), and primary sase tool run check 164d9e940e826f794f5c4f0c9a85c875 (exit 0; scoped tests passed). Recorded the clean-base TUI import-budget overage as a proposed follow-up citing sase-1ic. epic-symbols: none.

## Dependencies

- **Blocks:** [sase-1nf.10.1.9.1.6.3](sase-1nf.10.1.9.1.6.3.md) ✓ · ⧖ 2026-10-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.9.1.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.2/README.md) | [sase-1nf.10.1.9.1.6.2](sase-1nf.10.1.9.1.6.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1503d60`](https://github.com/sase-org/sase-core/commit/1503d604844a32a8a93e944addabb0887f8d9bc4) | feat(replay): accept merge-base bytes in recovery policy | [sase-1nf.10.1.9.1.6.2](sase-1nf.10.1.9.1.6.2.md) | 2026-10-21 12:08:48 EDT |
| sase | [`16d63cf`](https://github.com/sase-org/sase/commit/16d63cf9b0a4fc1a4e5c56a4660d2e45348ea0e8) | fix(agents-sync): preserve binary replay changes from merge base | [sase-1nf.10.1.9.1.6.2](sase-1nf.10.1.9.1.6.2.md) | 2026-10-21 12:12:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.9.1.6.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1nf.10.1.9.1.6.5][2] | Review the parent epic, phase evidence, and remaining acceptance scope before doing acceptance work | 1 |
| read-by | [agent:sase-1nf.10.1.9.1.6.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.5/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.land/README.md

<!-- sase:referenced-by:end -->
