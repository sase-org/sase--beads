# Bead: sase-1tz.1.1.7 — Report repeated managed-tmp reaper skips as one standing state

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.7` · **Size:** small
**Created:** 2026-11-19 07:28:42 EST · **Closed:** 2026-11-19 08:31:21 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

standing_skips: the managed_tmp_reap chop keeps refusing to reap entries it cannot fully inspect. It warns once when a skip appears or its reason changes, and logs again when the skip clears, instead of warning every pass.

## Notes

[2026-11-19T13:20:19Z · sase-1tz.1.1.7] Before-change athena baseline (2026-11-19): 34 managed_tmp_reap skipped log lines so far today; the audit observed about 195 recent repeated warnings for the preserved agent-tmp entry. Repeat after install: ssh athena 'DATE=$(date +%F); sed -r "s/\\x1B\\[[0-9;]*[mK]//g" ~/.sase/axe/lumberjacks/housekeeping/logs/output.log | grep -F "$DATE" | grep -F "managed_tmp_reap skipped:" | wc -l'. The chop now stores skips per root/entry/reason class, warns only for new or changed classes, logs clears once, and falls back to the prior bounded warnings when state is corrupt. Focused tests and sase tool run check passed.

[2026-11-19T13:31:21Z · sase-1tz.1.1.7] Implemented persistent managed-tmp standing skip reporting by root, entry, and normalized reason class. New or changed skips warn once, unchanged skips log a per-entry debug detail plus one summary, cleared skips log once, and corrupt state falls back to the previous bounded warnings. Focused regression tests and sase tool run check passed; athena's pre-change baseline and repeat-after-install command are recorded on this bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.7/README.md) | [sase-1tz.1.1.7](sase-1tz.1.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`06ae058`](https://github.com/sase-org/sase/commit/06ae058b5fff147bfb39ec81f58a6788141071a5) | feat(axe): report managed tmp skips as standing state | [sase-1tz.1.1.7](sase-1tz.1.1.7.md) | 2026-11-19 08:33:03 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.7][1] | Need all phase details, design links, and prior notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.7/README.md

<!-- sase:referenced-by:end -->
