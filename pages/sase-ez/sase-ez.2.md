# Bead: sase-ez.2 — Remove the Rust alias and re-prefix primitives

[Bead Pages](../README.md) / [sase-ez](README.md) / sase-ez.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sy/README.md) · **Assignee:** `sase-ez.2` · **Size:** large
**Created:** 2026-08-03 11:32:18 EDT
**Plan:** [202608/revert\_bead\_reprefix\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_bead_reprefix_epic.md)

## Description

core-revert: delete the sase-core bead re-prefix module, alias config field, and PyO3 migration bindings, restore pre-epic bead ID resolution semantics without regressing the retained single-pass detail read, and cut a patch release.

## Dependencies

- **Depends on:** [sase-ez.1](sase-ez.1.md) ✓
- **Blocks:** [sase-ez.5](sase-ez.5.md) ◐
