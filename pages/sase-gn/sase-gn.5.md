# Bead: sase-gn.5 — sase bead snooze and snooze-aware detail surfaces

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.5` · **Size:** medium
**Created:** 2026-08-06 19:27:50 EDT · **Closed:** 2026-08-06 21:13:22 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

bead-snooze-cli: add the snooze command and its time, +1, and reason arguments, extend status filters and query tokens, and show snooze metadata everywhere bead detail is rendered.

## Notes

[2026-08-07T01:13:22Z · sase-gn.5] just check green (all lint gates + scoped lane, 3762 passed). Added 'sase bead snooze' (-u/--until, -p/--plus-ones, -r/--reason, -c/--cancel, multi-ID with pre-flight resolution so a bad ID mutates nothing), shared snooze_time parser (30m/2h/1h30m/3d/1d12h or absolute ISO-8601) and snooze_presentation wording/glyph. Snooze metadata now renders in 'bead show' prose, JSON detail (stable 'snooze' key, null when not snoozed; golden CLI contracts regenerated), ACE Beads detail + list rows, and published bead pages. list/search gained the snoozed status choice and status:snoozed tokens while 'update --status snoozed' stays refused in favor of the new command. 32 new tests in test_cli_snooze.py and test_snooze_surfaces.py, plus a manual end-to-end CLI run against a scratch store.

## Dependencies

- **Depends on:** [sase-gn.4](sase-gn.4.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gn.8](sase-gn.8.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.5/README.md) | [sase-gn.5](sase-gn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b723ace`](https://github.com/sase-org/sase/commit/b723ace648b5c99923874f933c3f16e99cc1eeb9) | feat(bead): add sase bead snooze and snooze-aware detail surfaces | [sase-gn.5](sase-gn.5.md) | 2026-08-06 21:14:27 EDT |
