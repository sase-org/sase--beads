# Bead: sase-5t.4 — Phase 4 — First release: v0.1.0 on PyPI

[Bead Pages](../README.md) / [sase-5t](README.md) / sase-5t.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5t.4`
**Created:** 2026-07-12 21:44:39 UTC
**Plan:** [202607/symvision\_extraction\_1.md](https://github.com/sase-org/sase--plans/blob/main/202607/symvision_extraction_1.md)

## Description

Work in ~/projects/github/bbugyi200/symvision/. USER CHECKPOINT: before this phase runs, Bryan must register the symvision pending trusted publisher on pypi.org for bbugyi200/symvision, publish.yml, environment pypi. Verify the publisher or stop with a clear notification; then merge the release PR, watch publishing, and independently verify symvision 0.1.0.

## Notes

Release PR #1 merged as e865044f66dc1cc21909b7938d6f002e26cfd9ee. The PyPI trusted publisher was registered, and rerunning the failed jobs in Publish run 29211186259 succeeded. PyPI reports symvision 0.1.0, and a clean 'uv tool install symvision' produced a working CLI. Phase verified complete.

## Dependencies

- **Depends on:** [sase-5t.3](sase-5t.3.md) ✓
- **Blocks:** [sase-5t.5](sase-5t.5.md) ✓
