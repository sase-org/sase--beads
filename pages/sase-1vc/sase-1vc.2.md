# Bead: sase-1vc.2 — Do not re-run finalizers after they fail

[Bead Pages](../README.md) / [sase-1vc](README.md) / sase-1vc.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gj.md) · **Assignee:** `sase-1vc.2` · **Size:** medium
**Created:** 2026-11-26 07:38:27 EST · **Closed:** 2026-11-26 08:04:05 EST
**Plan:** [202611/linked\_repo\_commit\_finalization\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/linked_repo_commit_finalization_fixes.md)

## Description

finalizer_failure_not_provider_failure: keep success-path finalizer exceptions out of provider-failure finalization, and seed finalizer attempt numbers from attempts already on disk.

## Notes

[2026-11-26T13:04:05Z · sase-1vc.2] Separated success-path finalizer failures from provider-failure recovery in invoke_agent; preserved the finalizer error and normal error postprocessing without recording provider failure or retrying. Seeded controller attempt IDs above existing per-instance artifacts and progress events while retaining the per-phase attempt budget. Added regressions for staged handoff hold/provider-success behavior and persisted attempt numbering. Verified: focused tests passed; sase tool run check passed (scoped tests 10m 47s); the macro and prepared host completion callers do not retry after exceptions. Epic symbols reported no remaining entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vc.2/README.md) | [sase-1vc.2](sase-1vc.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6504926`](https://github.com/sase-org/sase/commit/650492693ad86489d4ba9bfc2c2b48bd14a43637) | fix(finalizers): preserve failure boundaries and attempt IDs | [sase-1vc.2](sase-1vc.2.md) | 2026-11-26 08:05:49 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vc.2][1] | Verify the assigned phase is closed before finalizing this turn | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vc.2/README.md

<!-- sase:referenced-by:end -->
