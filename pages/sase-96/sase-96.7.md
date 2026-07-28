# Bead: sase-96.7 — One-time reclamation of stuck space and orphaned dirents

[Bead Pages](../README.md) / [sase-96](README.md) / sase-96.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.7` · **Size:** small
**Created:** 2026-07-25 12:16:10 UTC
**Plan:** [202607/tmp\_space\_exhaustion.md](https://github.com/sase-org/sase--plans/blob/main/202607/tmp_space_exhaustion.md)

## Description

'One-time reclamation of stuck space and orphaned dirents' section: behind an explicit user confirmation gate, reclaim the multi-gigabyte trash directory and sweep the orphaned zero-byte lock files and bare temp entries out of /tmp.

## Notes

Gate custom-036e64e8-9dd9-4d73-adf1-45f7224caba9 approved cleanup+verify. /tmp/.Trash-1000 was already 0 KB. Removed stale >240m candidates: 2956 zero-byte lock files, 211 md archive files, and 4013 bare tmp entries. /tmp went from 847368 KB used / 11378 entries to 807276 KB used / 4198 entries in gate verification; follow-up check showed 902M used, 4212 entries, and 0 >240m candidates. Supervisor socket, tmux dir, and claude dir remained present.

## Dependencies

- **Depends on:** [sase-96.5](sase-96.5.md) ✓
