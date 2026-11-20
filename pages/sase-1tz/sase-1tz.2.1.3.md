# Bead: sase-1tz.2.1.3 — Turn repeated publication failures into standing alerts with backoff

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.3` · **Size:** medium
**Created:** 2026-11-19 11:13:26 EST · **Closed:** 2026-11-19 15:21:16 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

pub_standing: a sase-core decider keys publication failures by (project, signature) and reports only opened, changed, escalated, and cleared transitions. It backs off project-scoped failures. A standing store keeps true attempt counts and first/last-seen times, and one notification per alert fires only on transitions.

## Notes

[2026-11-19T19:55:33Z · sase-1tz.2.1.3] Measurement: standing store path ~/.sase/agent_publication/standing_alerts.json; after install, run the error_groups ring snippet plus cat ~/.sase/agent_publication/standing_alerts.json to confirm one alert per (project, signature) with true attempt counts

[2026-11-19T19:55:40Z · sase-1tz.2.1.3] PROPOSED FOLLOW-UP: sase-core standing change (decide_publication_standing + wire in agent_publication_recovery) is uncommitted in the linked sase-core checkout and sase-core-revision.txt still points at 5ad6013; the land flow must land the core commit first and move the pin past it, or CI builds core without the binding and the scheduler tick fails on AttributeError

[2026-11-19T20:20:49Z · sase-1tz.2.1.3] PROPOSED FOLLOW-UP: just check full-suite has 3 failures that reproduce identically on the clean base (verified via stash): test_cleanup_after_success_does_not_resurrect (mock lacks remaining_timeout kwarg the landed pub_cleanup call passes), test_artifact_directory_operation_sites_are_reviewed (unreviewed publication_scratch.py:sweep_publication_scratch), test_macro_string_literals_avoid_xprompt_terms (xprompt strings in tests/turns/test_workspace_retention_agents_scratch.py). All three come from landed sibling phase sase-1tz.2.1.4, none touch pub_standing files.

[2026-11-19T20:21:16Z · sase-1tz.2.1.3] pub_standing landed: Rust decide_publication_standing decider + binding (10 core unit tests + binding round-trip green, clippy/fmt clean), Python standing store/facade/job integration, 16 new job tests + updated ring-contract tests (39 targeted + 46 with doctor tests green). Verified: 20 ticks of one failure give 1 diagnostic, 1 notification, attempts=20; transitions report once; backoff skips drain+doorbell; clean pass clears quietly; full just check ran 62162 passed with only 3 failures proven pre-existing on the clean base (sibling 2.1.4 files, recorded as follow-up). Pin move + sase-core landing left for land flow (recorded as follow-up); Justfile drops the now-consumed normalize_error_signature epic-symbol row.

## Dependencies

- **Depends on:** [sase-1tz.2.1.1](sase-1tz.2.1.1.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.5](sase-1tz.2.1.5.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.7](sase-1tz.2.1.7.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.3/README.md) | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3c3263f`](https://github.com/sase-org/sase-core/commit/3c3263fb98cfe2185764f8e6ea6e3b0aaae0a40c) | feat(publication): add standing-alert decider with capped backoff | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 2026-11-19 15:22:42 EST |
| sase | [`5f719a5`](https://github.com/sase-org/sase/commit/5f719a5361c407086763f5f2dd71282755cc1713) | feat(agents-sync): report repeated publication failures as standing alerts with backoff | [sase-1tz.2.1.3](sase-1tz.2.1.3.md) | 2026-11-19 16:39:00 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1tz.3.1.1][2] | Find standing alert key/storage for prompt_prose failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.1/README.md

<!-- sase:referenced-by:end -->
