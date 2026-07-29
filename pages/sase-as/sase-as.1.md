# Bead: sase-as.1 — Copy mode on every Artifacts sub-tab

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.1

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.1` · **Size:** medium
**Created:** 2026-07-29 14:30:56 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

copy-mode: admit `copy_tab_content` on non-PR Artifacts sub-tabs, dispatch the second copy key on the active sub-tab before falling through to the tab id, add per-sub-tab copy key blocks and real copy menus for Commits, Plans, Chats, and Bugs, and make the COPY footer and its restore path sub-tab aware.

## Dependencies

- **Blocks:** [sase-as.2](sase-as.2.md) ◐
