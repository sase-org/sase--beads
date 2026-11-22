# Bead: sase-1ux.5 — NEEDS ATTENTION callout in session and clan detail panels, plus docs

[Bead Pages](../README.md) / [sase-1ux](README.md) / sase-1ux.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1f4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1f4.md) · **Assignee:** `sase-1ux.5` · **Size:** medium
**Created:** 2026-11-22 08:33:07 EST · **Closed:** 2026-11-22 15:22:21 EST
**Plan:** [202611/failed\_clan\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202611/failed_clan_visibility.md)

## Description

attention-callout: a left-barred NEEDS ATTENTION callout at the top of the session and clan detail panels. It says which turn failed, the cause, any not-adopted handoff, the downstream members it blocks, and the exact next step. The tribe NEEDS ATTENTION entry reuses it. Update the status, glyph, and monitor docs, and add panel goldens.

## Notes

[2026-11-22T20:22:07Z · sase-1ux.5] PROPOSED FOLLOW-UP: test_project_metadata_loaders_stay_at_reviewed_tui_worker_boundaries fails on the clean base tree too (possible owner sase-1uz per check triage); not caused by the attention-callout phase.

[2026-11-22T20:22:12Z · sase-1ux.5] PROPOSED FOLLOW-UP: test_sase_turn_terminology stale-phrase check is KNOWN-red on master (witness 213943eade02826f091c8cae17601735, cites notification-gates.md); not caused by the attention-callout phase.

[2026-11-22T20:22:21Z · sase-1ux.5] attention-callout done: shared NEEDS ATTENTION renderer (FailureFocus, cli_hint readopt) wired into session and clan detail panels, tribe entries reuse the cause line for structured failures, 4 reference docs updated, 2 panel goldens added and check-clean twice incl. TZ=UTC; just check 8929 passed with only 2 pre-existing failures (recorded as follow-ups)

## Dependencies

- **Depends on:** [sase-1ux.4](sase-1ux.4.md) ✓ · ⧖ 2026-11-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ux.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.5/README.md) | [sase-1ux.5](sase-1ux.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1d4f456`](https://github.com/sase-org/sase/commit/1d4f456f41a3a4b20c237bbdcb322d8b8a01f03f) | feat(tui): add NEEDS ATTENTION callout to session and clan detail panels | [sase-1ux.5](sase-1ux.5.md) | 2026-11-22 15:23:57 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ux.5][1] | Need phase scope | 4 |
| read-by | [agent:sase-1ux.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ux.land.md

<!-- sase:referenced-by:end -->
