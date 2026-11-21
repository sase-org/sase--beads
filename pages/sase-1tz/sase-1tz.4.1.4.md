# Bead: sase-1tz.4.1.4 — Add opt-in sidecar storage for oversize notification payloads in sase-core

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.4` · **Size:** medium
**Created:** 2026-11-20 14:00:22 EST · **Closed:** 2026-11-20 17:56:58 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

blob_store: sase-core stores action_data values and notes over a caller-supplied byte limit as content-addressed sidecar files, with a read binding. Compaction garbage-collects unreferenced sidecars and prunes broken files references. Default behavior is unchanged. Move the pin.

## Notes

[2026-11-20T22:45:55Z · sase-1tz.4.1.4] PROPOSED FOLLOW-UP: Refresh tests/completion/snapshots/cli_spec.json to match the current argparse tree; both completion snapshot tests fail identically with this bead’s changes stashed at clean HEAD 0386c59150. This recurrence matches the prior completion-drift task sase-1de and is also recorded by sase-1tz.4.1.6 note #4; no active task bead matches the current recurrence.

[2026-11-20T22:56:58Z · sase-1tz.4.1.4] Implemented opt-in content-addressed notification sidecars, resolver bindings, compaction GC/pruning, Python APIs, and storage docs. Verified linked sase-core `sase tool run check` succeeded; primary `just fmt` passed; focused primary regression suite passed (22 tests), including binding discovery, TUI import budget, helper APIs, triage ownership, disk footprint, and keymaps. The primary full check first exposed issues in our binding dispatch and TUI import closure; both were fixed and their focused tests now pass. Its two remaining completion-snapshot failures reproduce with all primary edits stashed at clean HEAD 0386c59150; recorded as a PROPOSED FOLLOW-UP citing sase-1de and sase-1tz.4.1.6 note #4. No --epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-1tz.4.1.3](sase-1tz.4.1.3.md) ✓ · ⧖ 2026-11-20
- **Blocks:** [sase-1tz.4.1.5](sase-1tz.4.1.5.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.4/README.md) | [sase-1tz.4.1.4](sase-1tz.4.1.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6524f37`](https://github.com/sase-org/sase-core/commit/6524f378e3d3078f2d1dc5dfbbbb5404a8e01e62) | feat(notifications): store oversized payloads in sidecars | [sase-1tz.4.1.4](sase-1tz.4.1.4.md) | 2026-11-20 17:58:29 EST |
| sase | [`6b444fc`](https://github.com/sase-org/sase/commit/6b444fcdefd3e9807aff39a922a1ec97641f796c) | feat(notifications): expose opt-in payload sidecars | [sase-1tz.4.1.4](sase-1tz.4.1.4.md) | 2026-11-20 18:00:36 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.4][1] | Need the phase scope, design file, decisions, and earlier work notes before implementation | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.4/README.md

<!-- sase:referenced-by:end -->
