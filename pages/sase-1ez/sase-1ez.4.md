# Bead: sase-1ez.4 — Take automatic gen-2 collection off the interactive path

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.4` · **Size:** medium
**Created:** 2026-10-02 16:45:01 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

idle-gc-policy: once startup loads settle and input first goes idle, run gc.collect() then gc.freeze() exactly once. Raise threshold2 to 10_000 on the classic three-generation collector. Run tagged full collections only when input has been quiet for 3 s, no prompt is active, and a collection is due, with 5-minute and RSS-growth backstops and an off-thread malloc_trim. Includes an env kill switch, a clean uninstall, and no install under the testing harness.

## Dependencies

- **Depends on:** [sase-1ez.1](sase-1ez.1.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.3](sase-1ez.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.4/README.md) | [sase-1ez.4](sase-1ez.4.md) | 0 |
