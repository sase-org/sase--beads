# Bead: sase-96.3 — Stop leaking ChangeSpec lock and archive siblings into the system temp dir

[Bead Pages](../README.md) / [sase-96](README.md) / sase-96.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.3` · **Size:** medium
**Created:** 2026-07-25 12:15:29 UTC
**Plan:** [202607/tmp\_space\_exhaustion.md](https://github.com/sase-org/sase--plans/blob/main/202607/tmp_space_exhaustion.md)

## Description

'Stop leaking ChangeSpec lock and archive siblings into the system temp dir' section: migrate the test call sites that create ProjectSpec temp files in the default system temp dir onto pytest's tmp_path, so the `.lock`, `-archive`, and `-archive.lock` siblings that sase creates alongside them land inside a directory pytest can collect.

## Notes

COMMIT: 782844a73

## Dependencies

- **Blocks:** [sase-96.6](sase-96.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.3/README.md) | [sase-96.3](sase-96.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4520b4c`](https://github.com/sase-org/sase/commit/4520b4cc353a8368fc1534dd92acf03f01f55324) | test: contain ChangeSpec temp artifacts (sase-96.3) | [sase-96.3](sase-96.3.md) | 2026-07-25 13:22:41 |
