# Bead: sase-14l.3 — An active settlement row keeps its agent row unread

[Bead Pages](../README.md) / [sase-14l](README.md) / sase-14l.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.17](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.17.md) · **Assignee:** `sase-14l.3` · **Size:** small
**Created:** 2026-09-20 16:56:58 EDT · **Closed:** 2026-09-20 19:46:44 EDT
**Plan:** [202609/epic\_launch\_read\_dismiss.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_launch_read_dismiss.md)

## Description

unread-projection: project active row-owned settlement notifications into agent row unread state so a settlement that arrives after the completion was read still has a read event to clear it.

## Notes

[2026-09-20T23:44:41Z · sase-14l.3] PROPOSED FOLLOW-UP: test_help_documents_the_options expects -e/--explain but notify rules help renders -e ID only (fails on pristine tree)

[2026-09-20T23:45:24Z · sase-14l.3] PROPOSED FOLLOW-UP: test shard timing table drifted 20.04% over the 20% gate (4217 files vs measured 3513; needs just refresh-shard-timings, fails on pristine tree)

[2026-09-20T23:46:44Z · sase-14l.3] unread-projection done: union helper active_row_owned_notification_keys added and wired into reconcile; 36/36 focused projection+match tests pass; just check lint gates green with only pre-existing failures (notify-rules help, shard drift, both reproduce on pristine tree, filed as PROPOSED FOLLOW-UP notes); symvision green after re-keying the settlement-predicate whitelist to parent sase-14l; epic-symbols clean

## Dependencies

- **Depends on:** [sase-14l.2](sase-14l.2.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-14l.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-14l.3/README.md) | [sase-14l.3](sase-14l.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`383f2c2`](https://github.com/sase-org/sase/commit/383f2c282791436ddcdf08d7ce9cb57604a7fd58) | feat(agents): add unread projection for settlement notifications | [sase-14l.3](sase-14l.3.md) | 2026-09-20 19:49:16 EDT |
