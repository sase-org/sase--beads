# Bead: sase-1ox.3 — Phase cli: \`sase agent load\` parity and legacy view cleanup

[Bead Pages](../README.md) / [sase-1ox](README.md) / sase-1ox.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14s.md) · **Assignee:** `sase-1ox.3` · **Size:** small
**Created:** 2026-10-27 10:48:22 EDT · **Closed:** 2026-10-27 15:24:24 EDT
**Plan:** [202610/capacity\_inspector\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/capacity_inspector_redesign.md)

## Description

cli: move `sase agent load` onto the tiered view per the cli_parity decision, delete legacy view fields with no remaining consumer, and update the runner-slots docs.

## Notes

[2026-10-27T19:24:24Z · sase-1ox.3] Verified CLI parity: sase agent load now prints headline, gauge, verdict, facts, Using/Queued/zero-weight/Not running sections, and ignored inactive counts; JSON unchanged. Deleted idle_groups, holdings, truncated/hidden, and expanded_idle_groups after grep showed no remaining src/ consumers. Kept headline/limit_line/snapshot_line/running_line/over_limit_note for the chip and inspector. Updated runner-slots and generated agent load docs. sase tool run check passed (9be52bdb); epic-symbols empty for sase-1ox.3.

## Dependencies

- **Depends on:** [sase-1ox.2](sase-1ox.2.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ox.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ox.3/README.md) | [sase-1ox.3](sase-1ox.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`daa96a5`](https://github.com/sase-org/sase/commit/daa96a5bd05c2eb23c8ce23e3dccb67af8b1afb0) | feat(cli): give sase agent load the inspector's tiered capacity view | [sase-1ox.3](sase-1ox.3.md) | 2026-10-27 15:26:16 EDT |
