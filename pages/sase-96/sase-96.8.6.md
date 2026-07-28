# Bead: sase-96.8.6 — Clean up the sase-core Rust test temp directories

[Bead Pages](../README.md) / [sase-96.8](sase-96.8.md) / sase-96.8.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Size:** small
**Created:** 2026-07-25 18:16:10 UTC · **Closed:** 2026-07-25 18:36:51 UTC
**Plan:** [202607/managed\_tmp\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202607/managed_tmp_reaping.md)

## Description

'Clean up the sase-core Rust test temp directories' section: change the four sase_core_py test helpers that create directories under std::env::temp_dir and never remove them to use tempfile::TempDir, and sweep the rest of the crates for the same pattern. sase-core-py-bead-* was named in the sase-96 plan.

## Dependencies

- **Blocks:** [sase-96.8.9](sase-96.8.9.md) ✓
