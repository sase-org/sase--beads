# Bead: sase-96.8.5 — Contain the sase-github handoff diff files

[Bead Pages](../README.md) / [sase-96.8](sase-96.8.md) / sase-96.8.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.8.5` · **Size:** small
**Created:** 2026-07-25 18:16:03 UTC · **Closed:** 2026-07-25 18:25:03 UTC
**Plan:** [202607/managed\_tmp\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202607/managed_tmp_reaping.md)

## Description

'Contain the sase-github handoff diff files' section: stop gh.yml from hardcoding mktemp /tmp/sase-gh-XXXXXX.diff and leaving it behind, and give new_pr_desc_get_context.py's pr_desc_ diff an explicit managed directory. Both were named in the sase-96 plan but fell outside the prodleaks phase's src/sase scope.

## Dependencies

- **Blocks:** [sase-96.8.9](sase-96.8.9.md) ✓
