# Bead: sase-96.5 — Stop \`rm\` from parking deleted /tmp data inside /tmp

[Bead Pages](../README.md) / [sase-96](README.md) / sase-96.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.5` · **Size:** small
**Created:** 2026-07-25 12:15:49 UTC · **Closed:** 2026-07-25 13:12:17 UTC
**Plan:** [202607/tmp\_space\_exhaustion.md](https://github.com/sase-org/sase--plans/blob/main/202607/tmp_space_exhaustion.md)

## Description

'Stop `rm` from parking deleted /tmp data inside /tmp' section: change the dotfiles-level `rm`-to-`trash` alias so paths under /tmp and $TMPDIR are deleted outright instead of moved into a trash directory that lives on the same tmpfs, and document the rule for agents.

## Notes

COMMIT: 1b135404

## Dependencies

- **Blocks:** [sase-96.7](sase-96.7.md) ✓
