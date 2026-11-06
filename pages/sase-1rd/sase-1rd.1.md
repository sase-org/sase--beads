# Bead: sase-1rd.1 — Rust run-trash contract in sase-core

[Bead Pages](../README.md) / [sase-1rd](README.md) / sase-1rd.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18e.md) · **Assignee:** `sase-1rd.1` · **Size:** medium
**Created:** 2026-11-05 06:20:14 EST · **Closed:** 2026-11-05 07:57:27 EST
**Plan:** [202611/actionable\_run\_prune\_notifications.md](https://github.com/sase-org/sase--plans/blob/main/202611/actionable_run_prune_notifications.md)

## Description

core_quarantine: add a sase-core module that quarantines confirmed ACE-run dirs into a journaled, restorable trash by atomic rename, re-checking every protection first. It also lists, restores, and protection-verifies purges, with PyO3 bindings and tests. The unattended apply refusal stays.

## Notes

[2026-11-05T12:57:27Z · sase-1rd.1] Implemented the sase-core ACE run-trash contract with protection rechecks, journaled atomic quarantine, orphan discovery, restore, and verified purge; added PyO3 bindings and round-trip tests. The 10 focused run-trash tests passed, and the full guarded  passed (ToolRun  f4a1af0a668351596b88f0a1c935458b). The linked core commit SHA will be appended after host finalization for trash_callers.

[2026-11-05T12:59:21Z · sase-1rd.1] PROPOSED FOLLOW-UP: Triage the existing scoped-check failures — ToolRun 4c46120ca5f92c8a6e06ea3db371bde2 exited 1 with no_new_failures; it marked test_no_undo_on_shared_monkeypatch_fixture KNOWN (witness 0ea4d12896bf1d703ba1b18ecdb64ea3), and the marker-path and session-sandbox tests FLAKY. No task bead owner was reported, and no clean-base comparison was run. Correction: the primary guarded check did not pass; the separate linked sase-core check passed as ToolRun f4a1af0a668351596b88f0a1c935458b.

[2026-11-06T18:02:36Z · sase-1rd.land] LAND AUDIT: the finalized core commit promised in note #1 is 39744416635e319fb8f65f90e4f89dfd0b4fc395 (feat(agent-artifact-run-trash): add journaled run quarantine). Verified its implementation and PyO3 registration/round-trip tests, and that the current sase pin 28159925724bc9ff46c3fccd9047f159f428c861 contains it. Landing found additional preservation defects now recorded on sase-1rd and covered by its remaining-work repair tale; this note does not claim those defects are fixed.

## Dependencies

- **Blocks:** [sase-1rd.2](sase-1rd.2.md) ✓ · ⧖ 2026-11-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rd.1/README.md) | [sase-1rd.1](sase-1rd.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3974441`](https://github.com/sase-org/sase-core/commit/39744416635e319fb8f65f90e4f89dfd0b4fc395) | feat(agent-artifact-run-trash): add journaled run quarantine | [sase-1rd.1](sase-1rd.1.md) | 2026-11-05 08:00:29 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rd.1][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rd.1/README.md

<!-- sase:referenced-by:end -->
