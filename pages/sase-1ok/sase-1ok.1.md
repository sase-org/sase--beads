# Bead: sase-1ok.1 — Let the stranded-work collector see single-turn sessions

[Bead Pages](../README.md) / [sase-1ok](README.md) / sase-1ok.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14p](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14p.md) · **Assignee:** `sase-1ok.1` · **Size:** medium
**Created:** 2026-10-26 18:10:49 EDT · **Closed:** 2026-10-26 20:08:15 EDT
**Plan:** [202610/stranded\_phase\_detection\_and\_wrong\_bead\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_phase_detection_and_wrong_bead_guard.md)

## Description

stranded-root-members: add an agent_name candidate-filter field to the sase-core artifact index and query agent_session OR agent_name from the stranded collector, so a session's root member (agent_session null) is no longer reported unknown/no_records.

## Notes

[2026-10-27T00:07:50Z · sase-1ok.1] PROPOSED FOLLOW-UP: capacity scan tests assume fixture pid 11111 is alive — test_capacity_only_skips_done_dirs_and_keeps_active_ones + 2 runner-slot capacity tests fail wherever pid 11111 is absent since sase-1oj.1 never-live prune; fixtures need stubbed liveness or live pid

[2026-10-27T00:07:59Z · sase-1ok.1] PROPOSED FOLLOW-UP: sase_gateway ipc test listener_creates_private_socket_and_rejects_symlink flaked once under parallel check load, passes alone and per-package; file a flake bead if it recurs

[2026-10-27T00:08:15Z · sase-1ok.1] stranded-root-members done. sase-core: AgentName candidate-filter variant (index_wire.rs) reading indexed agent_name, carried on IndexedCandidateRow (selection.rs/candidates.rs), case-insensitive Equals; new agent_name_filter.rs tests pass; core gate green (fmt/features/clippy/lib 5437/integration/py 353/gateway 243/macrolsp/script-test; one gateway IPC load flake green on rerun). sase: stranded_facts queries any(session==assignee, name==assignee), exact recheck + artifact_dir dedupe kept; CandidateField literal extended. 6 new single-turn tests pass (query shape, stranded/unclosed past grace, parent-epic blocked via live land waiter, live WAITING owned, dedupe, multi-member parity) + 33 neighboring stranded tests pass. just check: all lint gates green; 3 capacity-test failures are pre-existing env issues (fixture pid 11111 absent + sase-1oj.1 prune), identical on pristine-base build, filed as follow-ups. epic-symbols clean. Docs need no change (unknown wording still accurate). sase-core-revision.txt left for declaration: no new core SHA exists until the host commits the sase-core sibling; pin bump rides with that commit.

## Dependencies

- **Blocks:** [sase-1ok.2](sase-1ok.2.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ok.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ok.1/README.md) | [sase-1ok.1](sase-1ok.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@03dce1f`](https://github.com/sase-org/sase-core/commit/03dce1f20be40ad7d127dba3ec52c387d5352b5c) | feat(agent-scan): add AgentName candidate-filter variant | [sase-1ok.1](sase-1ok.1.md) | 2026-10-26 20:09:43 EDT |
| sase | [`98cb07e`](https://github.com/sase-org/sase/commit/98cb07ebb8f56aedc9d5f9c044687c8ee342d93a) | fix(stranded): find single-turn root members via any(session, name) query | [sase-1ok.1](sase-1ok.1.md) | 2026-10-26 20:36:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oh.4.1.3][1] | Cite existing tracking for capacity_only scan test failure | 1 |
| read-by | [agent:sase-1ok.1][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1ok.2][3] | Confirm the already recorded capacity-scan follow-up and whether it names a tracking task bead | 1 |
| read-by | [agent:sase-1ok.3][4] | Cite existing KNOWN capacity-test follow-up from sibling phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ok.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ok.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ok.3/README.md

<!-- sase:referenced-by:end -->
