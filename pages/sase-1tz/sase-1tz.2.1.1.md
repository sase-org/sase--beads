# Bead: sase-1tz.2.1.1 — Group the scheduler error ring by signature with durable interval counts

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.1` · **Size:** medium
**Created:** 2026-11-19 11:13:26 EST · **Closed:** 2026-11-19 12:47:11 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

error_groups: a sase-core normalizer turns error text into a stable signature. append_error keeps a durable per-interval counter keyed by (routine, job, signature) next to a signature-fair sample ring. Failed or corrupt writes are counted and logged once instead of dropped.

## Notes

[2026-11-19T16:56:34Z · sase-1tz.2.1.1] error_groups baseline (2026-11-19, read-only, pre-install). athena ring: 100 rows, agent_publication 44, workspace_sdd_clone_recovery 22, artifact_retention 20; span 2026-11-14T19:54 to 2026-11-19T10:18. apollo ring: 100 rows, agent_publication 61, workspace_sdd_clone_recovery 7, artifact_link_backfill 7, sidecar_auto_sync 5, stale_running_cleanup 4; span 2026-11-17T07:22 to 2026-11-19T11:40. error_counts.json absent on both (created on next append after install). After-install command: python3 -c "import json,collections;e=json.load(open($HOME/.sase/axe/recent_errors.json));print(len(e),collections.Counter(x['job'] for x in e).most_common(5))" plus cat ~/.sase/axe/error_counts.json | head -c 2000.

[2026-11-19T17:46:39Z · sase-1tz.2.1.1] PROPOSED FOLLOW-UP: tests/fakey/test_gate_capacity_custom_e2e.py::test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent failed once in the 42-minute loaded full-suite check run (57s under xdist parallel load) and passes standalone in 7s; looks like a load flake, unrelated to error_groups (imports only gate-turn machinery).

[2026-11-19T17:47:11Z · sase-1tz.2.1.1] error_groups landed and verified. sase-core: new axe_error module (normalize_error_signature masking paths/SHAs/agent@sha/UUIDs/timestamps/durations/pids/run-ids/bare ints, group_axe_errors keyed by routine/job/signature) with 8/8 Rust golden tests passing, incl. deferred-prompt archives sharing one signature across agents. Python: append_error now updates durable error_counts.json (schema 1, interval_start/total/write_failures/corrupt_files/per-cause groups) before the signature-fair ring (100 cap, 5 per signature); corrupt files quarantined aside as *.corrupt-* and counted; write failures counted in-process and folded in on next success, logged once per kind; read_errors contract unchanged; new read_error_counts accessor. Tests: 21/21 in tests/test_axe_error_groups.py + tests/test_axe_state.py (incl. extended concurrent-spawn exact totals). Full just check (escalated to full suite: 62125 passed) green on all lint gates incl. symvision with new --epic-symbol rows for sase-1tz.2.1.2 (group_errors/normalize_error_signature/axe_error_wire_schema_version); single unrelated flake in gate-capacity e2e passes standalone, recorded as PROPOSED FOLLOW-UP. Docs updated (scheduler-housekeeping.md, scheduler.md). Baselines noted on bead. NOT done by worker: sase-core-revision.txt pin move and commits in both checkouts left for host finalizers (host commits sase-core first, then ratchets pin).

## Dependencies

- **Blocks:** [sase-1tz.2.1.2](sase-1tz.2.1.2.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.3](sase-1tz.2.1.3.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.1/README.md) | [sase-1tz.2.1.1](sase-1tz.2.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3a32a23`](https://github.com/sase-org/sase-core/commit/3a32a233f0fb6fb8c894008eb52b407b2e50b4a9) | feat(axe-error): add volatile-token normalizer and signature grouping | [sase-1tz.2.1.1](sase-1tz.2.1.1.md) | 2026-11-19 12:48:47 EST |
| sase | [`1ae81b4`](https://github.com/sase-org/sase/commit/1ae81b40987b9bd19fefc8abc926eb703e17108d) | feat(axe): add durable error counts with signature grouping | [sase-1tz.2.1.1](sase-1tz.2.1.1.md) | 2026-11-19 12:50:24 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1tz.2.1.2][2] | Need error_groups landed work to build digest_render on | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md

<!-- sase:referenced-by:end -->
