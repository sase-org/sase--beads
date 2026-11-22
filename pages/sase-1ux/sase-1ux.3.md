# Bead: sase-1ux.3 — One failure-aware session rollup that every surface consumes

[Bead Pages](../README.md) / [sase-1ux](README.md) / sase-1ux.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1f4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1f4.md) · **Assignee:** `sase-1ux.3` · **Size:** medium
**Created:** 2026-11-22 08:33:07 EST · **Closed:** 2026-11-22 12:50:02 EST
**Plan:** [202611/failed\_clan\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202611/failed_clan_visibility.md)

## Description

session-rollup: not-adopted members never count as started work. A failed turn stays the session's state until a real later turn supersedes it, for both plan and plain roots. Clan roster, waves, tribe summary, BY_STATUS, and count chips all read the one session rollup. A `FailureFocus` record carries the cause to presentation, and a cross-surface consistency test pins it all.

## Notes

[2026-11-22T17:49:30Z · sase-1ux.3] PROPOSED FOLLOW-UP: Triage clean-base `just check` failures — run 6bc8ab67fad6f19482706022e05845e3 reported seven failures; six reproduced on clean HEAD 1c4c89f6b4: project-display metadata allowlist, stale terminology audit, system-clock display audit, monitor-settlement replay (`_PreparedApplyHarness` lacks `_agents_token_reload_kind`), and both artifact-marker mutation audits. No task bead was linked in triage. The seventh failure, the anonymous hijack canary, passed on clean base and appears intermittent.

[2026-11-22T17:50:02Z · sase-1ux.3] Implemented unified root session rollups and failure focus across status apply, clan roster, waves, and tribe summaries. Focused regressions: 27 passed. Full guarded check: 15,810 passed, 7 failed; six failures reproduce on clean HEAD and are recorded as a proposed follow-up, while the anonymous hijack canary passed on clean base. Lint, Symvision, SASE validation, and plan checks passed.

## Dependencies

- **Depends on:** [sase-1ux.2](sase-1ux.2.md) ✓ · ⧖ 2026-11-22
- **Blocks:** [sase-1ux.4](sase-1ux.4.md) ✓ · ⧖ 2026-11-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ux.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.3/README.md) | [sase-1ux.3](sase-1ux.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3dc72dd`](https://github.com/sase-org/sase/commit/3dc72ddd4c3fe4e6b1f16746151dbaf639083ecb) | feat(tui): unify failure-aware session rollups | [sase-1ux.3](sase-1ux.3.md) | 2026-11-22 12:51:38 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ux.3][1] | Confirm phase scope, decisions, and recorded baseline follow-up before close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.3/README.md

<!-- sase:referenced-by:end -->
