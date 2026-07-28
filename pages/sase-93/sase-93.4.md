# Bead: sase-93.4 — Remove the host \`$HOME\` dependency from the axe editor visual snapshots

[Bead Pages](../README.md) / [sase-93](README.md) / sase-93.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-93.4` · **Size:** small
**Created:** 2026-07-25 11:27:24 UTC · **Closed:** 2026-07-25 13:07:23 UTC
**Plan:** [202607/restore\_green\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202607/restore_green_ci.md)

## Description

'Phase: visual-home-path' section: derive the axe writable-scope fixture path from the real home directory so the tilde abbreviation renders identically on every host, then regenerate the seven affected goldens.

## Notes

COMMIT: bd5baf22c

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-93.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-93.4/README.md) | [sase-93.4](sase-93.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d58f7b0`](https://github.com/sase-org/sase/commit/d58f7b062094e42d4cf580626050cf74fcf39097) | test(visual): drop host home paths from visual fixtures (sase-93.4) | [sase-93.4](sase-93.4.md) | 2026-07-25 13:08:24 |
