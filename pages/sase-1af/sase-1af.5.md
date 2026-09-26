# Bead: sase-1af.5 — Complete Services source-panel visual and performance verification

[Bead Pages](../README.md) / [sase-1af](README.md) / sase-1af.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1af.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1af.land.md) · **Assignee:** `sase-1af.5.land`
**Created:** 2026-09-26 11:43:24 EDT · **Closed:** 2026-09-26 12:58:06 EDT
**Plan:** [202609/services\_source\_visual\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_source_visual_completion.md)

## Description

Cover the promised source combinations and terminal sizes with reviewed PNG goldens, and verify navigation and refresh cost before sase-1af lands.

## Notes

[2026-09-26T16:58:06Z · sase-1af.5.land] Verified sase-1af.5.1 against commit 8c9653df0 and the Services PNG goldens. Fixtures stamp explicit origins: Builtin+User (hooks user, checks builtin with a failed smoke run), all-sources (plugin sentinels), builtin-only, and empty routines. Tests cover 120x40 for those three source combinations, 100x30 and 70x36 for Builtin+User, J/K focus, and services-tab key-to-paint samples. Inspected goldens: panel order is Service Procs, User, Plugin, Builtin; builtin checks stays collapsed with the !1 badge; plugin and user panels appear only for those sources; empty routines keeps the add hint and the stopped scheduler; 100x30 and narrow titles stay legible, with narrow titles truncating. Title building reads in-memory caches only; service log reads go through asyncio.to_thread, off the paint path. The epic commit is tests and goldens only, so there is no presentation change to re-trace for idle refresh. The epic bead had no notes of its own.

Integration since epic creation, excluding 8c9653df0: 4ef716648 (proc-rename test repair), 221d72a13 (agent node-finder; fold-filter results stay identical), 9e8a65ad2 (verdict receipts), and e922c424e (prompt model-shortcut completion). None edit Services source panels, these fixtures, or these goldens, so nothing needed to adopt this coverage.

Follow-up sase-1af.5.1 note #1 (just check lint feature-flags rule 7: closed sase-1ad still defining card_blocks) is not caused by this test-only diff. It is the same unfinished retirement as flag bead sase-1ad, owned by in-progress epic sase-19x: phase .9 claimed decks/flag.py was deleted, but no commit in this clone mentions sase-19x.9 or sase-1ad. Recorded +1 --verified-after-close, which reopened sase-1ad, and DISCOVERED ISSUE notes on sase-19x. Recheck of tools/check_feature_flags exits 0; the only output is a rule 8 warning for in-flight sase-1ar (legacy_sase_shell_syntax, sase-1ab.3), which is not this follow-up. No new task. epic-symbols for sase-1af.5: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1af.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1af.5.land/README.md) | [sase-1af.5](sase-1af.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@d3e7e96`](https://github.com/sase-org/sase--plans/commit/d3e7e96f90eefb0525a233a776033e139b6ce0bc) | docs(plans): mark landed Services source epics done | [sase-1af.5](sase-1af.5.md) | 2026-09-26 13:07:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1af.5.1][1] | Need parent epic scope for phase work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1af.5.1/README.md

<!-- sase:referenced-by:end -->
