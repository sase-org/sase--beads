# Bead: sase-5l.12 — doctor: add ulimits, inotify, truecolor deep checks

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.12

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.12`
**Created:** 2026-07-08 05:14:42 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add deep checks. resources.ulimits: compare soft RLIMIT_NOFILE and RLIMIT_NPROC against a floor derived from configured runner concurrency. resources.inotify (Linux-only): read /proc/sys/fs/inotify/* and WARN when watch/instance limits are likely to force ACE inotify watchers into polling. terminal.truecolor (deep, low priority): WARN only when image-preview fidelity matters. Add tests. See research section 11 and the epic plan design file.

## Notes

COMMIT: f15c9a337

## Dependencies

- **Depends on:** [sase-5l.11](sase-5l.11.md) ✓
- **Blocks:** [sase-5l.13](sase-5l.13.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.12/README.md) | [sase-5l.12](sase-5l.12.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f15c9a3`](https://github.com/sase-org/sase/commit/f15c9a33758bf82d0cc1e4a4372b5edd5d8b38ed) | feat(doctor): add deep host limit checks (sase-5l.12) | [sase-5l.12](sase-5l.12.md) | 2026-07-08 21:07:57 |
